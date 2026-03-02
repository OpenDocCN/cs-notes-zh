# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p13 -13-Ph CS 219A Lecture 11 Quantum Circuits.zh_en -BV1KgffBoEUc_p13-

![](img/2c62424ec54f3eb2d58573da3379db0c_0.png)

Okay， welcome back， Quaum friends。 Good to see you again。 It's good to be seen。

 I appreciate your loyalty。 Amazingly， we have reached Chapt 11 of。😊，Physics， Comp Science 219 A。

 the term is just whizzing by， I guess that means we're having fun。So， let's， without。

Further shenanigans get going。Okay， so we began at the end of the last lecture to discuss quantum circuits。

 we will continue with that today and in fact on into lecture 12 for a while as well last time building on the previous discussion of classical circuits we talked about randomize and reversible classical circuits which set us up for introducing the quantum circuit model。

 which we had just gotten around to formulating at the end of the previous lecture and today I want to address some basic questions about the quantum circuit model of computation。

For one thing， we know quantum gates being unitary transformations live in a continuum。

 and we'd like to understand if we're experimental physicists or computer engineers just how accurately the gates in our hardware need to approximate the ideal gates in some quantum circuit of interest in order to give us computationally useful results。

We'd like to see。How complex。From the perspective of how large a quantum circuit is required are typical unitary transformation。

 you remembered， we asked a similar question about Boolean。Functions。

 the size of the circuits needed to compute typical boolean functions。

 there's a quantum version of that question that we'd like to consider。

We'd like to know if there's some。Bound on the classical resources that are needed to simulate a quantum computer。

 Can we say it can be done with。Such and such amount of memory or some specified number of gates。

And we'd like to understand more deeply the concept of a universal gate in the quantum circuit model and we'll be getting to all of those things today。

 the discussion of universal gates will continue into the next lecture as well。

So let's just reorient ourselves， remember the formulation of the quantum circuit model that we discussed last time。

The arena in which the computation takes place is the Hilbert space。

Of n qubits spanned by the two to the n computational basis states of N qubits。

 it's important for the model that we had not just very large Hilbert space。

 but also a preferred decomposition into small subsystems that's what allows us to talk about complexity because in the circuit model our gates only act on some small specified number of qubits and。

We are。Are interested in the question， how many gates do we have to put together to solve some computational problem。

 We assume we can initialize the computer in product state like the state in which all the qubits are in the state 0。

And we have hardwired into our machine or into our model some set of quantum gates， some finite set。

 which are universal and universal means that by putting circuits together built from those gates。

 we can get as close as we want to any unitary transformation， acting on the inqubits。

We're taking it for granted that there's a classical computer behind the scenes controlling the quantum computer formally that comes in because we would like to discuss complexity in the circuit model and for that purpose we need to speak of。

Families of circuits that are uniform and that notion of uniformity will be defined by whether the circuits can be constructed by a Tring machine efficiently。

 a classical Tring machine designs the circuit which is then executed to perform the quantum computation and in the end。

 of course we need to read out a result which we do by measuring one or more qubits in the model。

 it's enough to consider measuring only one， particularly if our goal is to compute some boolean function。

And of course， that being a quantum measurement， that final result is probabilistic。

 not deterministic， given a quantum circuit when we read out the answer bit at the end。

We won't definitely get a zero or one， but rather there will be some probability distribution for those outcomes。

Now there isn't anything in this model which I've now completely specified that can't be simulated by a classical computer。

 but as far as we know that simulation is not possible efficiently。

The intuition is that because the Hilbert space is so vast inside， the size。

 the quantum gates are acting on this two to the n dimensional Hilbert space。And。

It takes a lot of resources to keep track of how the state is evolving in that vast space。

Now we can define a complexity class as。The class of problems。

 decision problems that we can decide efficiently with the quantum circuit model。

 that class is called BQP Boed error， quantum polynomial time。

 and we believe that we can prove it from first principles that BQP is a larger class than BPP that quantum computers can efficiently do things that ordinary classical computers。

 even randomized ones cannot do。All right， let's take up the question of accuracy。

I might have some ideal quantum circuit， which if I could execute it would solve some problem of interest。

But in a real device， we're not going to be able to hit those unitary transformations right on the nose。

 There will always be some error since the。Unitary transformations live in a continuum and they can't be specified to an infinite number of bits of precision。

So when we speak of。Approximating a ideal circuit with real hardware the gates which are applied are not exactly the ideal gates。

 they have some small error and so if I put together capital T gates and get some final state which will then be measured to get a final outcome the actual state is not going to be the same as the ideal state okay now those errors are going to accumulate over the course of the execution of the circuit and we'd like to understand how bad the news is about that。

Now I'm considering these noisy gates to be unitary transformations。

 I claim i'm entitled to do that as we've discussed before because while they might actually be say。

Trace preserving completely positive maps I can always add an environment for each one of the gates and consider a unitary acting on the quantum data in the computer and the environment to describe that operation So in that case。

 you should think of this approximate state is not just being a state of。The computer itself。

 but the computer and its environment in the ideal case， there is。

 if you like a state of the environment， but the ideal gates don't act on it at all。

 so if we have an initial product state of the data in the environment that never changes。Now。

 these actual noisy unitary transformations will differ from the ideal one by some small error。

 some deviation， an operator， which I called E sub T for the gate， the teeth gate in the circuit。

And I'm going to characterize the size of that or you or using the super norm。

 the operator norm of that deviation E of T。 you remember what that means it's the。

The largest singular value of the operator E 17。And let's suppose that we built our hardware well enough that for each one of the gates。

 that error is bounded by some hopefully small constant， let's call it epsilon。

 and now we'd like to know when we put together capital T of these gates if we want to get about the right answer。

 how small do we need that error to be and in particular。

 how is it going to scale with the size of the circuit with the total number of gates。

Now remember in the end we're going to perform a measurement and it's enough to just measure a single qubit。

 but let's suppose just for the sake of argument that we actually measure all the qubits。

 in fact I'm going to imagine measuring all the qubits of the environment as well the environment that I need to describe the noisy operations in the end I might only be interested in the marginal probability distribution when I sum over all the other measure bits except for the answer bit I care about but that marginal distribution if the well I guess let me put it this way if the complete distribution for all the possible outcomes is close to the ideal one that will certainly be true for that marginal distribution so it's enough for me to consider the requirement that the complete distribution when I measure everything is close to the ideal one so what is what is the probability distribution I'm talking about well we're measuring in some complete basis。

The final state after we've done， we finished applying all the gates in the circuit and the probability of getting a particular computational basis state as an outcome is just the inner product squared of that computational basis state with the final state of the computer at the end of。

The execution of the circuit。That's the ideal probability distribution。

 that's what we're shooting for。But the actual probability distribution that shouldn't be an A that should be an X。

 sorry， is the inner product of computational basis state X and also including potentially additional。

Bits of the environment with the noisy state。 And so I want these to be not too far far apart from one another。

 And I think， you know， from an exercise that the nice way of quantifying what probability distributions are is to use the。

The one norm for the L1 norm for probability distributions up to a factor of one half。

 which we include by convention。Norm is just the sum over all the possible outcomes of the difference of the probabilities given by the two distributions。

 absolute value。And what you showed in the exercise is that that's less than or equal to the boy。

This shouldThere's a bar missing on the。Kt hears。Okay， sorry about that。

 But this is just the difference between two state vectors， the ideal state and the noisy state。

 So the idea is that we want that to be small。 Okay， let's go back。

Now remember in the the way we defined BQP is that we wanted to get the correct answer with the probability at least two thirds。

 but actually getting the correct answer with the probability of success one half plus some small constant would be good enough because we could amplify it by running the computation some modest number of times。

 so if the ideal circuit gets the right answer with probability two thirds， I would like the。

Noisy probability distribution to have an error， which is。

 say less than 16 so that I'll still get the right answer for the answer bit with probability one half plus some positive constant。

So I'd like this to be less than some constant number， you know， let 16 or something like that。

And so how are we going to do that， well， we have to look at what the error is when we add up together the errors in all of the gates in the circuit。

There's kind of a convenient way of organizing that， so it's easy to get a bound on it。

So what I'm calling utilda， that's the noisy circuit， it's the product of all the noisy gates。

The product of all the use of T tildes， each one of the use of T tildes is a use of t plus an E sub T。

So I'm going to organize that this way first I pull out all the terms that don't have any errors at all。

 that's the ideal circuit。And then I pull out all the terms in which I have the error E1 acting at the first gate in the circuit。

 And then I include all other。Configurations for the rest of the circuit could be an error or could be ideal。

 So that term is just E1 acting at the first gate and then the noisy utilitiess acting on gates 2 through capital T。

And then the next term is one in which there's definitely an error in the second gate。

 but I don't want to double count， so I don't want to include the case in which there's also an error in the first place because I already counted that so I have now the ideal gate。

In the hut。Time window 1， the error in one time window 2。

 and then the noisy gate for time step 3 through capital T。 And I go on like that。

 The next term is the one in which we definitely have an error in。

The third gate to avoid double counting， I'm then going to consider only the ideal unitary in the first time step in the second。

 but the noisy unitaries from then on。And so on。 so you can see I wind up getting a difference between the ideal unitary。

 which is this first term and the noisy unitary， which is the sum of all the terms。

Which is a sum of T terms， and I'd like to get a bound on the soup norm of that total error。

Because that's going to tell me how much the final state vector or give me a bound on how much the final state vector deviates from the ideal state vector。

And now let's look at each one of these terms， well each one of them is a product of unitaries because remember the noisy use and the ideal use are both unitaries。

 except there's one error inserted in each one of the terms everything else is unitary now the soup normor of a unitary transformation is one right because its eigenvalues are all phases with absolute value one and when you take the soup normm of a product of operators。

 we know we can bound that by the product of the soup normorms。

And so each one of these terms has a soup norm， which is just bounded by the soup norm of the corresponding error。

The super Noror E1 or E2 or E3， okay？And they're all capital T， such terms。And。

I know the soup norm of a sum can be bounded by the sum of the soup norms。

 So if each one of the terms has a soup norm， which is bounded by epsilon， because remember。

 we said that。E of T as a soup norm bounded by epsilon。

 then the sum of them all has a soup norm bounded by capital T times epsilon。

And we want to make sure that that's less than some。Small constant of order 1， Delta。

 And for that purpose， we want the error epsilon to be less than deelta over capital T。

 because when we have T gates， the error is going to get capital T times bigger。

 as you might have guessed。Okay， so we don't have to have incredibly accurate quantum gates to get an answer with an acceptly small deviation from the ideal case。

 but we do need better and in general we're going to need better and better dates if we want to do longer and longer computations so the news isn't terrible but it's still not very good because if I wanted to solve some problem people might really be interested in like。

Factoring a really large number or solving some chemistry problem。 I might need billions of gates。

 And so I would like to have an error per date in order to get an acceptable answer in that case。

Which is like 10 to the -9。 That's really， really hard。

To do with hardware that we have now or that we're likely to have for quite some time。

The best error rates for two cubid gates now are。At the under ideal conditions at the 10 to the minus three level。

 what I just said was a factor of a million better than that to do。

 say or even or even worse if I want to factor a large number or something like that。And but。

the good news is that the theory of quantum error correction and fault tolerant quantum computation。

 which we're not going to talk about this term， but which I think you'll hear about next term。

 that tells us that if we're willing to pay a price in overhead to have the size of the circuit increase by some factor which goes like a power of a logarithm。

Of the size of the ideal circuit。Then it turns out to actually be acceptable to have the error per gate less than some sufficiently small constant that constant is well it's。

Probably around 1% something like that， so if you can get gates to that accuracy and you can put together lots and lots of qubits and lots and lots of gates。

 then you should be able to solve heart problems to it。To feel comfortable。

 I'd like that error rate per day to be more like 10 to the -3 than 1%， but in principle。

 maybe 1% would be enough， but the overhead cost would be would be pretty bad in that case。

So that's the story of accuracy。Now let's ask the question。

 since it's interesting to consider how things might be different in the quantum case。

 we asked the question in the classical case， you know。

 how big a circuit do we need to compute a typical Boolean function？We were。Horrified。

 well maybe not really， but it was notable that most Boolean functions require really。

 really large circuits exponential in the number of bits of the input to the problem。

And so from that point of view， most problems， the amutation of most boolean functions is hard。

In the real world， we're only going to care about the ones that we can solve a lot more efficiently than with a circuit size that's exponential in that。

It's a similar story in the quantum case。Hilbert space is really big。And what that means is that。

The space of unitaries is really big and if you wanted to be able to come as close as we please or well。

 with some reasonably small error to every possible unitary transformation on acting acting on endqubits。

 that's a lot of unitary transformations you can。Estimate how many this way。

We consider the unitary group acting in a capital n dimensional space we have in mind little N qubits。

 so capital N is an exponentially large space two to the end。

And now every point in this gray ball that I've drawn is a unitary transformation， of course。

 there are an uncountable number of them。But I'd be satisfied to be able to approximate each one of the unitary transformations with some small error。

Delta in the soup norm。 So I'd like to cover the space of unitaries with little balls with have have radius。

A Delta and if I can cover the whole unitary， then for any unitary you're interested in in UN。

It'll be inside one of those balls， okay， so it can be approximated to within the air delta by some unitary。

 which you can think of as being the the center of that ball。The question is。

 how many balls do we need， Well， the balls have some small radius， I've called it Delta。

The whole unitary group has some large radius， but I can just take that radius to be some number of order one。

And。Now， the thing is that the dimensionality is extremely high and so the volume of a ball scales like the radius of the ball to a power。

 which is the dimension times some geometrical constant。

 which I'm not even going to care about because it's going to drop out。

I consider some ball which has some constant radius called it C， and it is a volume。

 which is some numerical constant。Time C raised to a power， which is the dimension。

 the dimension of the unitary group in a space which is capital and dimensional。

 is capital n squared。So the volume of the big ball goes like some constant。To the power n squared。

The volume of each one of the little balls， which just as a radius delta goes like that same geometrical constant times little delta to the power capital n squared because that's the dimension of the space。

And so the total volume of the unitary group or something that might be smaller than the full unitary group。

 but is completely contained within it。Divided by the volume of each one of the balls is going to go like the ratio of the order1 radius C to the small radius delta raised to a power。

 the dimensionality of the group and squared。For us。

 capital n means two to the little n because we're considering unqubits。 so that's some number。

 which is。Big than one， if Delta is small， raise to an enormous power。

 Ra or the power2 to the two to the n。Okay。So。The number of balls that we need to cover the whole space。

Increases with the number of qubits doubly exponentially in N。Okay。

 we saw the same kind of thing when we were counting the Boolean functions on end bits。Now。

I'd like to compare that to the number of circuits that I can construct with some specified size。

 some specified number of gates， and I won't try to estimate that prairie precisely because for this argument。

 I really don't need to。But the circuit consists of a sequence of gates。

 Each one of those gates has chosen from some。Finite alphabet of possible gates and then each one of the gates in that alphabet acts on some constant number of qubits so if I take into account。

Each time I add another gate to the circuit。Which gate it is in my finite set and which set of qubits it axon that's just going to be some factor which goes each time I have another gate like some polynomial in。

 okay？Like maybe if I'm considering two qubbit gates， it goes like n squared， the number of ways。

 you know， I can choose a pair of qubits at the end。That the gate axon。

 And I do that altogether capital T times in constructing the circuit。

 So it's some polynomial and n raised to the powered T。

 That's the number of different circuits there are。Okay。And if I wanted to have a circuit。

For every ball。So that tea is large enough and you know I've。Chsn my circuits cleverly enough。

So that I have for every ball， circuit contained in that ball。Then。

I need for this number of circuits to be larger than the number of balls to make the comparison。

 let's take logarithms， so if I take the logarithm of the number of circuits。Um， that's。

Going to go that times a T goes like polyen， so I want T to be larger than the number of balls divided by polyen。

 sorry， the log of the number of balls。And if I take the log of this doly exponentially small number。

 I get the factor2 to the two n in front and then times the log of C over deelta。

 So in order to cover all the balls， the number。Of circuits has to be doubly exponentially large and for that I'm going to need a circuit size which is exponential in the number of qubits。

 aside from this log polyn factor， it increases with the number of qubits like two to the 2N。Okay。

If I were stuck to just。The circuits of polynomial size I'd be only able to reach only a very tiny fraction of all the balls。

 Most of the unitary group would be completely unexplored if I only considered some polynomial。

Size to the circuits Okay， there are lots of circuits of polynomial size。

 but not nearly enough to reach all the nooks and crannies of Hilbert space Hilbert space is just too darn big。

Actually， the same remark applies if I consider not circuits in some ideal computational model。

 but if I consider physics。I could say the same sort of thing about if I start out with some simple initial state。

Like a product state， and then I'm going to let it evolve according to some Hamiltonian for some amount of time。

And if that Hamiltonian is what I'll call a physically reasonable Hamiltonian。

 we'll talk more about what I mean by that a little later。

 but I've sort of explained the idea before， physics is local。

 so a Hamiltonian which is physically reasonable， should be a sum of terms where all the terms act on some constant number of qubits。

And by an argument similar to this one， it turns out that in order to reach all the possible states or realize all the possible unitaries。

We need to let the system evolve for a time which is exponential in the system size。

 exponential in the number of qubits。Nobody wants to wait that long and if you only wait an amount of time。

 which is polynomial in the number of qubits， then you'll be doomed to explore just a tiny fraction of all the possible states in Hilbert space。

Now， you notice I made kind of a subtle shift there from talking about unitaries to talking about states。

 actually there's an interesting difference。Between classical and quantum complexity here。

If I consider and bits。I could consider like a reversible circuit that takes n bits to end bits。

 we talked about that。But the final bit string is always going to be something very simple。

 it's only n bits long， so it's something that's easy to write down。

 it doesn't normally make much sense to talk about the complexity of a bit string or in other words the complexity is just linear in n。

 however long it takes you to print out a bunch of zeros and ones。

But quantum states are different than that。They don't have succinct classical descriptions as we've discussed。

And so for a typical quantum state in the Hilber space of Nqubits。

 it takes a quantum circuit if I start out with the product state of exponential size to reach that state most。

Quantum states and Hilbert space are so complex that well never be able to reach them no matter how powerful our quantum engineers are in the future。

 Hilbert space is just too big。Now， let's think for a minute about what we would do if we wanted to simulate a quantum circuit using a classical computation model like the classical circuit model。

 Well I remarked on that on that already， I think I said， well。

 you can think of the gates as being unitary transformations acting on。This state vector。

Which lives in a two to the n dimensional Hilbert space， so in the end。

 a unitary is going to be a two to the n by two to the n matrix。And you can。

Calculate what it is if you have enough memory by just multiplying together a lot of matrices。

 if you have some circuit each circuit is。Each gate in the circuit is a unitary transformation。

 the result of applying T gates is the product of T unitary transformations。

 you can just multiply them out and that is indeed a valid way of doing the simulation of the quantum circuit by a classical one you notice it takes a lot of memory because I need to store a description of a vector in two to the n dimensional Hilbert space so I would need an exponential NN amount of memory to do that。

You can ask the question， what if we just don't have that much memory， are we sunk。

 is it impossible in that case to do a simulation of the quantum circuit with the classical circuit or can we somehow get by with an amount of memory which increases just polynomially with the number of qubits rather than exponentially？

Well the answer is that yes， you can you can simulate a quantum circuit。

 even if you only have a polynomial amount of memory。

 so the way to say that in complexity theory language is that the class BQP of problems that you can solve。

Efficiently in。The quantum circuit model is contained in the class piece space。

 a very big computational class of problems that can be solved if you have a polynomial amount of memory。

嗯。Okay， well， let's see how that works。What we want our simulation to do on the classical computer is to actually this is more than it really has to do。

 but it's enough。Let's say we would like it to compute the probability。Of getting。

A particular computational basis state as an outcome。

 if we measured all the qubits after we apply a unitary circuit to the initial state of all zeros。

 No， we might only be interested in。One particular answer bit， but that's okay each time we。Well。

 in principle， we could we could figure out all the probabilities for the exponentially large number of。

Possible outputs。And then we can sum them up and sum them all up to accumulate them all that is。

 I'm summing over all the qubits that aren't being measured because I'm only interested in the marginal distribution for the answer bit。

Summing all those up doesn't require a big amount of memory because I don't have to store all the sum mans each time I add another term to the sum。

 I only have to keep the running total in order to go on to the next step and add another term to the sum so I can certainly do that with a modest amount of memory。

But for some fixed x， I want to be able to compute this quantity， okay？

And this unitary is a circuit consisting of capital T gates and it's implicit if I'm talking about BQP that capital T is polynomial and N。

 this is a polynomial size quantum circuit that we're trying to simulate。And now we use a knee trick。

We have。You here expressed its product。Going right to left of U1 times u2， blah， blah， blah， U T -1。

 U T just a product of unitaries。 And then in between each。Pair of unitaries。

 I'm going to insert a sum over all the computational basis states。 So I insert the projection on x1。

 but then I sum x1 over2 to the n values here。And so I've indicated that is I'm summing over all the x of t's where x of t is going to run from x of little t is going to run from x of1 to capital to x of capital t minus1。

So here I'm summing x1 overall possible bit stringing values and then between U2 and U3。

 I insert a projection onto x2 and I sum that overall possible values and so on， okay。

And so now I've expressed this matrix element that I'm going to want to square to find the probability。

As if you like， a sum over many computational paths in which the bit string， which starts at zero。

 gets a map to x1 and then to x2 and then to x3 and so on， finally to x t minus1。

 and then in the end to x。But I have to sum over all the paths and there are an exponentially large number of them。

 in fact。In principle， I have two to the n possibilities for x of little t at each step。

 and I have all together。Well， t minus1 intermediate values， and so I've got a sum up。

An exponentially large number of these products for each computational path， for each fixed X1， x2。

 blah blah X T -1。 I have to take the product of these matrix elements of unitaries。

And and then I have to sum over all of those terms， like I said。

 I can accumulate the sum without having a huge amount of memory。

 but we want to be sure that for calculating each one of the terms in the sum we don't need a large amount of memory so what I've described is something that physicists will recognize as the Feynman path integral formulation of quantum mechanics I've just described unitary evolution by introducing some intermediate times and summing overall possible states at those intermediate times。

 and here is my very crude artist conception of a sum over histories。

 I'm considering the initial bit value zero。Progressing after capital T steps to the final value x over lots of different possible intermediate choices and each one of these little trajectories is supposed to represent a particular way of choosing the intermediate values of the x of T's。

And for each one of those， there's some complex number which I obtained by this product and I have to sum all those up。

Okay， so the number of complex numbers I have to sum up is pretty big it's two to the end because that's what。

That's the number of possible choices for these intermediate expertises。At each time。

 but they're t minus one times， so altogether two to the n times t minus1。嗯。And。Yeah。

 so I have to consider that for each computational path。I have to。

 once I've fixed all of those expertises， multiply these numbers together， capital T numbers。

 complex numbers that I have to multiply together， actually most of those numbers are zero that makes life a little simpler。

There's some classical circuit that I want to do the job of computing each one of the factors in this product。

 which is just the matrix element between some computational state on the right here called Y and a computational state on the left here called Z of one of our unitary gates。

But the unitary gates only act on some small constant number of qubits。 Let's say two。

 And so this matrix element is going to vanish unless all of the。Bit in the string。

Defining Y and Z are the same except for the ones corresponding to the qubits on which this gate x non trivially so most of these guys are zero and the ones that aren't zero I can store in a classical memory。

And I can make a call to that classical memory whenever I need one of these matrix elements。

 so I have to have the matrix elements stored。Of all of the gates in my。Universal set of unitaries。

Between Bi stringings on the right and on the left。

 but that's not really so many matrix elements because it's real I can really just think of this as a too cuid unitary because。

All the otherqubits have to be fixed or it's going to vanish。Okay。And。

So we need to estimate each one of these matrix elements or of the classical circuit that I call the classical memory。

Is going to have an accuracy for each one of those。

 which is something like scales like one over capital t times  two to the minus little n t minus1。

Because I'm going to take a product of T of these， and then I'm going to sum up all together two to the nt minus one terms。

 and I want to be able to do that with some constant accuracy， as explained earlier。

 some constant accuracy is good enough。Okay。But it's not really such a hard task。

 at least in terms of memory usage， I got lots and lots of summing to do。

 I have to have enough precision in my computation of the matrix elements so that the errors are sufficiently small。

 but that just means I need a number of bits of precision。

 which is the log of this number plus some sufficiently large constant。

And so that means a number of bits of precision， which really just goes like Nt。

 maybe times a log factor。And that's not so much memory。

 So we can do the whole simulation by summing up lots and lots and lots of terms。

 We have to compute like crazy。 And we're kind of trading off some。😊。

Memory for computation time using less memory， but computing water。

 because we have to sum up so many terms， but we never have to store lots of bits in order to get the answer。

 So that's what I mean by saying。That you can simulate the quantum circuit。In polynomial space。

 BQP is contained in peace space。Okay， so now let's talk more about universal gates。

In our computational model， we assume that there's a finite instruction set。

 so that's formalized in the model by saying that our gates in the circuit are chosen from some finite alphabet。

And you might say if you're an experimental physicist， there's no good reason for that because。

 you know， you can perform any singlequbit unitary， for example。

Rotate the blockpher any way you want acting on an atom by fooling around with your laser and I guess that's true。

I mentioned， I think it was last time。That when we get to the story of fault tolerant quantum computation。

 it really is important that we consider a finite instruction set because although the physical unitaries that you can do in the lab or in hardware are an uncomfortableable set。

 the ones that you can do fault tolerantly that act on encoded information in a way that doesn't spread errors badly or doesn't compromise the error correcting power of the code really is just a discrete set。

 So it's a good thing that we're able to deal with a formal model of computation in which the。

Quantum gates that we choose from is just some constant number。

So what does it mean for the gate set to be universal。

 it means that we can do anything we want with these gates， if we put aside the complexity。

 what does it mean to do anything we want well we could certainly perform any possible computation。

They could be performed with you know， an ideal gate of。Arbitrary unitaries。

 if I can approximate any unitary transformation acting on the Nqubits by building a circuit from these gates。

 so that's what we're going to mean by universality。

That we can come as close as we want to any unitary acting on N qubits。By building a circuit。

 and I was just reminding you here that in our model。

 each one of these gates acts on some constant number of qubits like maybe two。And。Well。

 in the model， we allow the。Gay to act on any pair of qubits in the device。

 Irespective of how they' are located in space。 In other words， when the formal model。

 we don't worry about the geometry of how thequbits are laid out in space。

 It wouldn't be that big a deal， if we did。If in fact。

 the qubits were arranged in a one dimensional line wanted to and I can only do nearest neighbor gates and one of the qubits is at the 17th place and the other qubit is at the 53rd place。

I wouldn't be able to get them to interact directly。

 but I wouldn't be able to swap neighboring qubits or very closely approximate a swap if I have a universal gate set。

Even if I could only do gates on nearest neighbors， I'd be able to swap， swap， swap， swap。

 swap until QBbit 17 is sitting right next Qbit 18。And then I can do my two cubic data on those two。

 and then I can swap， swap， swap， swap and put。The moving qubit back to place 54 or whatever it was I said before。

 okay？So we might as well just assume that there is no geometric locality constraint for the purpose of discussing complexity in the model because doing all those swaps isn't so expensive。

 it certainly doesn't turn a polynomial size circuit into a super polynomial size one。

Sometimes we can settle for something less than universality called encoded universality。

Maybe because of symmetries or some such reason， we can't really come arbitrarily close to all the unitaries acting on incubbits。

 but some a subgroup of the unitaries， but as long as that's an exponentially large subgroup then that's good enough for。

然。Accessing the power of quantum computation。Now I'm going to make a distinction between a couple of different kinds of universality。

First of all， I speak of exact universality and what I mean by that is I'm changing the rules a little now。

 I'm not considering a finite construction set， but I consider some class of quantum gates in a perhaps uncountable set。

And exact universality means that by building circuits from those gates。

 I can hit on the nose exactly any unitary I want。So in a statement of exact universality。

 for example， is that two， there should be two cubic gates， not two gates。

Two cubit gates are exactly universal， okay？In other words， if I。

Have any unitary that I want to reach acting on N qubits。

 then by putting together a suitable circuit of。Gates where each gate just acts on a pair of qubits。

 I can realize that unitary exactly。In fact， if I can do any singlequbit gate。

 that's exactly universal if I have one fixed。Entangling to cubicate， it has to be entangling。

 it can't take product states to product states。But as long as it's entangling。

 and if I can let that gate act on any pair of qubits。Then together with single cubbit gates。

 that's exactly universal， we can use that to build up any unitary we want。

So it doesn't take much in the form of interaction between qubits in order to rule the world and get to the whole unitary group。

 it only takes twoqubit interactions and in fact， nothing special about those two qubit interactions。

 anything will do as long as it creates entanglement。Another notion is generic entanglement。

 which while I was sort of touching on a minute ago。

 but now I want to say it in the context of a finite instruction set。In fact。

 a single two qubit date。In almost all cases， that means except for a set of measure zero。

The non entangling gates in particular。For twoqubbit gates。

 just using that gate and nothing else as long as it can act on any pair of qubits。

 that's enough for universality。 So universality is a very general thing。 It's hard to avoid it。

If you don't have any interactions and you're stuck with single cubic gates。

 well that's obviously not unitary because it's。Only going to take product states to product states。

 but once you can entangle， you can build up any unitary。Now in the problems。

 you're going to be looking at particular universal gate sets to see that they're universal or try to understand why it's true。

 that there are finite gate sets which are universal but。If you believe。

 and I'm going to show you in the rest of the lecture that the statement of exact universality is true。

 then if you can come as close as you want to any twoqubit unitary， that's going to be enough。

To build up any unitary， once we know that the two cuid unitaries are exactly universal。

 then if we can approximate any two cuid unitary， then then we're golden。

And here are some examples of。Gate sets that are universal。I'm using a notation。

 which I can't recall whether I used it before this lambmbda notation when I write Lambda of U。

It means a note in saying it in words， I might say controlled you。

It means that you is applied to the second qubit if the first qubit is one and the identity is applied。

 if the first qubit is zero， so remember we talked about the controlled not gate as an example of that。

That's the lambda of Xga， it applies x。To the second qubit。

 if the first qubit is one then the identity otherwise。

And I can also consider gates with more controls like lambda squared U or controlled。

 controlled U means now it's a three qubbit gate， and it applies u to the third qubit only if the first two qubits are in the state 11。

Okay， so it has two control bits。Examples of universal gate sets。Are these first。

 let me tell you what I mean by HS& T。These are all single qubit unitaries， H is the headamardd。

Interchanges the x and the z basis for a qubit， it's written as a two by two matrix， it's this one，1。

1，1， minus one。The S gate is a rotation。About the z axis by the angle pi over 2 written as a2 by2 matrix。

 it's this one。 it's diagonal with eigenvalues， E to the plus or minus I pi over 4。

 and t is just the square root of S。 It's the rotation about the z axis of the block spheree by an angle pi over 4。

As a two by two matrix it's diagonal with eigenvalues e to the plus or minus I pi over8 and I think in the homework what I'm calling S here I might have called p or p was the same as s up to an overall phase S seems to be the more standard notation now so I'm using s here and I think in the type lecture notes as well。

So anyway， what are these universal gate sets， if you can do a controlled S， the twoqubbit gate。

 which applies s when the control is one and you can apply a head of mark。

 that's enough for universality。Another example， if you can do a controlled not gate。

Lambex control not， and you can also do the two。Well， the single cubic gateates H and T。

The headamard， which flips the X and z basis， the T， which rotates by pi over4 about the Z axis。

 that's also universal。Or if you can do the H and the S。Well。

 that's not enough for universality even acting on a single qubit by themselves。

 but if you throw in the Tflly gate， which here remember the Tly gate is the controlled controlled knot or in the notation I'm using here lambda squared x if you have a Tflly and you've got a head a Martin and S that's enough for universality as well and you'll。

See some of these things from doing the problems。But what I want to talk about now is why I claim that two cubic gates are exactly universal。

Let's see how that argument goes， the argument is in two steps。

The first step is to show that any unitary transformation can be expressed as a product of what I'm going to call two by two unitaries。

 I'll explain what that means in a minute。And then the second step is to take these two by two unitaries and express them as circuits of two Cuban unitaries。

SoThe two steps together mean that any unitary can be expressed as a circuit of twoqubit unitaries。

What I mean by a two by two unitary acting on a capital n dimensional space。

Is a unitary which only has a two non zero off diagonal entries， so you can think about it this way。

 it's a direct sum of a unitary acting on two of our computational basis states in this m dimensional vector space。

Add direct sum of that with the identity acting on the other n minus2。Basis states， okay？

That's what I mean by two by two unitary。It acts on trivially only on two of the computational basis states a2 cubit unitary is something different。

 It's a direct product of a unitary acting on two qubits and the identity acting on the remaining and minus2 qubits。

 Notice I'm。Using capital N here and little N here， if we consider the。

Hilbert space of little inqubits。That's two to the n dimensional， so for little Nqubits。

Capital n here is two to the n， so what I'm calling a two by two unitary acting on little n qubits。

Is one which。ItRe acts on the span of two of the computational basis states and acts trivially on all the other computational basis states。

Whereas a two cubit unitary。Is a direct product of a two qubit transformation。

Acting on a particular pair of qubits with product with the identity acting on the other little n minus two qubits。

Okay， so let's see why this statement。One is true that every unitary is a product of two by two unitaries。

Well， let's we have。Capital N basis states in this capital n dimensional space。

 I'm going to label them 012， blah， blah， blah up to capital n minus1。

So consider the unitary acting on the basis state labeled zero， it's some vector。Which， of course。

 I can expand in terms of the basis。Now I claim。That there's unitary。That I can construct。

 I'm calling a w sub zero。Which is a product of n minus12 by two unitaries with the property。That。

U of acting on zero is the same thing as W sub zero acting on zero。Why do I say that？Well。

Let's consider a。Product of two by two unitaries reject in the following way。Acting on zero。

 it's going to take zero to a if it acts on trivially on zero。

To a linear combination of two of the basis states。 So I'm going to call the other basis state in。

In its image one。So there's a unitary which maps。Which is2 by2 which map  zero to a00 plus b01 for some b0 a0 is the coefficient of0 here in this result of applying U to computational basis state zero so that's what the first two by two unitary does。

Then another two by two unitary comes along and it's going to take。B sub 0，1 to a sub 1。

1 plus B sub 1，2。 Okay， this is the same a sub 1 as appears in this linear combination。嗯。

For the result of U applied to 0。And there's going to be some unitary that does that because。

 of course， I'm guaranteed that since you is unitary， this guy has norm1。

 and so B01 is going to have a norm。嗯。Well， less than one。

 but the result of applying u to0 is going to have a coefficient of one。Which is can't be any larger。

Then one， so for B01， it can't be any larger than b0 and we know that a0 squared plus b0 squared is equal to1 I'm talking too much。

 I think it should be clear to you that there's some unitary which takes this b01 to a1 that's the coefficient of1 in this linear combination here。

Plus some other complex number B1 times a state I'll call2。

And then there's another two by two unitary， and it takes B1，2 to a2，2 plus。B sub 2，3， and so on。

 And I keep going that way， applying one， two by two unitary after another。

Until I have completely constructed this expansion of the state resulting from U applying to zero。

So that means I have achieved with that product of two by two unitarianaries。

 what I claim this product has the property that when acting on zero。

 it gives the same thing as when you x on zero。The total number of two by two unitaries I needed is well just the number of steps here。

 if you count them up， you can see there were n minus1 steps to completely construct this linear combination as an image of a product of two by two unitaries。

Okay， so what do we do next， So now let's consider the unitary。

 which is the result of applying the inverse of w0 to U。Okay， well。

 that's going to have the property， let's call it u1 that acting on zero， it gives zero。So in effect。

 u1 has become a we had an n by n unitary U， but u1 is really an n minus1 by n minus one unitary。

It really acts on the orthogonal complement of the state zero。

 and now I can do that same construction as before。And I can find a W1。

 which now is going to be a product of n minus22 by two unitaries such that W1 acting on the。

Basis state one。Gives the same result as you want acting on the basis state1。And U1 and W1， well。

 U1 has the property that。It。Acting on zero would give zero。

 and I could choose w1 to have that property too because all of the two by two unitaries are chosen to act trivially on zero。

Okay。And so now I can define a use of two。Which is the result of applying first U1 and then W1 inverse。

 or recall callinging what U1 is， that's you。And then moving from right to left。W sub zero。

 inverse W sub 1 inverse u2 is now and then minus2 by n minus2 unitary。

That is it's going to preserve the basis state1 and preserve the basis of state  zero。

 and then I can take that n minus2 by n minus2。AUnary and a chops dimension down again。

And I do that with a product of n minus3 two by two unitaries。Okay， so what we when we're all done。

We have。Obtained。哎呀。Unitary， which X on。That's exactly the way you does， in other words。In each step。

 we obtain the identity acting on all the basis states we've taken care of so far。

 plus some nontri unitary acting on its orthogonal complement。

And after altogether together n minus1 steps， we have only the identity left。

And that means that this。APro is going to be the identity or in other words we've expressed you。

As just taking up， oh， I guess some of these were supposed to be in versus。I'm sorry。

 this should be inverse and this should be inverse。

And that means multiplying by first Wn minus2 on the left， and Wn minus3 and so on。

 we have U equals W0， W1， Wn minus3， W and of blah， blah， blah up to Wn minus2。

So each one of these guys is a product of two by two unitaries and U has been expressed as product of the Ws。

And if you count up， if you're interested， how many2 by two unitaries we needed and the first step we needed n -1 and the next step。

 n -2 and so on altogether， it adds up to one half n times n -1，2 by two unitaries， that's enough。To。

Construct any unitary acting on the capital n dimensional。Viectctor space。

So that was step one of the argument， remember step two。

Is to show that every two by two unitary can be constructed as a circuit of twoqubit unitaries。

How's that going to work？Well， to see that， this circuit identity is going to be very handy。

My notation， which I think I。Explain before。Is that this is my notation for a controlled controlled gate。

It means that only if x and y are both equal to one。

Is a non trivialvi unitary applied to third qubit？And which here I'm calling U squared。

And here I've written that as a circuit。Which is supposed to be read from a left to right。

 that is the gate furthest to the left is the one that acts first。And this means a controlled U。

This means a controlled n， I could have called this an X。

 but this is kind of a standard notation for a controlled n or controlled X。

This is the controlled UA joint or controlled inverse of U。Controlled not。

 And this is the controlled U controlled by the first qubit here。

 the controlled U and controlled U inverse are controlled by the second qubit。

 And I claim that this is an equality。 This circuit of five gates gives this transformation。

So let's verify that。Well， what we have to do is count the number of times that U is applied to the third qubit。

Given that x and y are computational basis states。嗯。Well， okay。Let's look at the circuit。

Here we have a controlled Y。 so that means when y is equal to1， u is applied to the third qubit。

 So I wrote Y here。Which is one if one is if y is 1 and0， yhi is0。

And then we have this control not here， and that puts into the second bit register the value of the x or of x and y。

 in other words， y gets flipped as if x is1 and not if x is 0。And then the。

Inverse of u is applied controlled by x。X or Y。 So I wrote minus X X or y as the number of times U is applied。

 In other words， I had a U。 and then this number of U inverses。

 So the net number of u is y minus X X or y so far， but we're not done。This controlled not。

U does what the first control not did， and that's good so that the X and y will be preserved as was implied by writing this controlled controlled U squared。

And then I have one more gate， which is controlled by the first bit。

 and that means the number of views applied is going to be x。

It's going to be1 effects x is1 and zero， effects is zero。

Now it's handy to write the XO that Xor is the same thing as addition modo 2。

Of the bits x and y is x plus y minus2 xy。So in other words， if x and y are both1， this is0。

 it becomes 1 plus 1 minus2， if x and y are both0 it's0， if x is 1 and y is0 or y is 1 and x is 0。

 then it's 1， it's the same thing as an x or。So now it's easy to see how things add up。

Because I have a y minus a y and x minus an x and the number of times U is applied is2 x y。

So that means u squared is applied if xy is equal to 1。

 and that's true only if x and y are equal to1。So that's why the circuit identity is true。

And once we see how it works。It's easy to generalize it。

So here we used the controlled not and the controlled U and the controlled U inverse。

 and we saw that we could build this controlled controlled U square。In a similar way， if I have a。

Controlled m minus1 times u and lambda。M minus-1 x。And a controlled U and a controlled U inverse。

 that's enough for me to make the。U squared controlled by M bits。

And it's essentially the same circuit。The controlled not gates I want to replace by controlled M minus1 times x gates。

And for this last control U， I want to replace that by the U controlled by M minus1 bits。

And then the calculation is going to be almost the same as before。

The first controlled U is going to apply u to the last bit。X M times once if x of M is 1，0 if xm is0。

And then the last。Controlled you because it's controlled。

By M minus1 bits the number of times it's supplied is just the product of the first M minus1 bits。

 x1， x2 product blah， blah， blah， x M minus1 only if they're all one in other words is the U applied。

And then。I have this U inverse here， and I'm going to subtract some used away the number of times the U inverse is applied。

Is determined by the X or。Of this last bit or last control bit， XM。

And the product of the first m minus1 bits， because remember I replace the controlled x by this x controlled by m minus1 bit。

 so it applies x only if all of x1 through x minus1 are equal to 1。

 so the number of times U inverses applied is the x or of xm and the product of x1 through x minus1。

And now I use the same identity as before to write the X or as the sum of Xm plus the product of the Xjs minus twice the product of these two things。

 which now is going to be the product x1x2 bla of XM。So the same thing happens as before。

 more or less。The XM gets canceled， the product of x1 through xm minus1 gets canceled。

 and what's left is twice the product of x1 through Xm。So that means u squared is applied if。

X1 is equal to 1， x2 is equal to 1， blah， blah， blah to Xm is equal to1。

 That's the construction of the controlled M times u squared。From these other gates， okay？

So now you see， I can use this procedure recursively。Every unitary has a square root。

So suppose I can do any controlled unitary you like， a controlled unitary is a twoqubbit gate。

 so I'm imagining I can do any twoqubbit gate I want then I can certainly do a controlled unitary acting on a pair of qubits。

So from this circuit identity， what it's telling me is I can just take u to be the square root of V。

 and then I can construct a a and controlled V from a circuit and all of the gates in this circuit are two qubbit gates。

 okay？But I can construct any controlled controlled B that way。Okay， in particular。

 I can make it toughly that way。Ptophaly is just a controlled x。

But then I can use this generalized step to get to unitaries that are controlled by three bits， okay？

Because once I have the controlled controlled V， I can use the controlled controlled V and these other gates I know how to construct。

To get the controlled， controlled， control V。Okay。And so building up step by step， I can get any。

Unitary controlled by M bits for any M up to n minus1 if I have all nqubits， okay？

Remember that if we can do toths， toths are universal。For reversible classical computation。

And that means we might need。A few un syllabs for this。

But that means that we can realize any permutation。

Of the computational basis states with a circuit of tola。Okay。

 because that's what reversible classical computation is。

 it's a permutation of the computational basis states。Okay。

So starting just with these two  cubbit gates。I can do any permutation because I only need tophaes for that of the computational basis states。

And I can do a controlled M of V for any unitary V and for anyM。嗯。From1 up to n-1。

 if they're all together and qubits。Okay。So we're almost done。In particular。

 that means we know how to build from two Cupid gates。

The unitary V applied to the target qubit controlled by n minus1 qubits。No。In a system within qubits。

 that is when I'm calling。A two by two unitary。Okay。

It acts non trivially only on the span of two bit strings。

It doesn't do anything unless the first n-1 bits are all equal to one。

So it nontrivial action is on the span of。N minus11s，0， and n1s。

And it's just the identity acting on the orthogonal complement。 That's a 2 by two unitary。 Okay。

 It just acts on the span of two vectors in our。Basis set， it's the identity acting on the rest。

Now I'd like to be able to do a arbitrary two by two unitary。Using my。Universal gates set。

The two cubit unitaries。Well， I've explained how we do this， how we do the control n minus1 times V。

Using that gate set of two Cuban unitaries， I've explained how we do the tophaly from the tophaly。

 we can do any permutation of。The computational basis states。

I'd like to do a two by two unitary on an arbitrary pair of basis states。

X and Y are both strings of N bits labeled by strings of N bits。So consider some permutation sigma。

Which takes X。To the string， all ones， except the last bit is0 and takes y to the string all ones。

And consider constructing sigma。 I can make that out of To the gates。Control then minus1 V。

Which we've seen how to construct out of two cubic gates and then the inverse of sigma。Okay， well。

 that is just the two by two unitary that acts on the bit strings x and y。

Because X and Y get mapped to these two guys。The controlled V act on。Those two strings。

And then inverting sigma sends the basis back to what it was to start with。

The effect of that is just the unitary V acting on the span of x and Y。

So that completes the argument。We've seen。That。Two cubic gates allow us to get any two by two unitary and we saw that any by that any unitary transformation can be reached。

From a product of 2 by2 unitaries， that shows that the two cubic gates are an exactly universal set。

So far we haven't talked about the case of finite universal gate sets。

And I'll say something about that in the next lecture。So until then。Take care of yourself， be well。

 and I look forward to seeing you again soon。Okay。

![](img/2c62424ec54f3eb2d58573da3379db0c_2.png)

Bye， bye。