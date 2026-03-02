# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p20 -20-Ph CS 219A Lecture 18 Local Hamiltonian.zh_en -BV1KgffBoEUc_p20-

![](img/759709973aad70be5d452e3ad1924356_0.png)

Okay， here we go again， welcome back to Ph Comp Science 219A quantum computationut。

Last time we talked about using quantum computers to address quantum problems， including。

Measuring the energy of a system described by a local Hamiltonian。And。

H described a way of addressing that problem。Which often works。But it doesn't always work。 And today。

 I'm going to try to explain why it sometimes fails， namely that。

Finding the ground state of a local Hamiltonian and measuring the energy of that state。

 Sometimes those are really hard problems， which we don't expect to be able to solve efficiently。

Even with a quantum computer， so you remember。We talked last time about using phase estimation to measure。

The eigenvalues of a local Hamiltonian， and that works if we can prepare a state which has a sufficiently large overlap with the energy eigenstate。

 whose energy we want to measure， and if our criterion is。

 as we usually assume that we want to be able to solve the problem with high success probability。

With a circuit， a quantum circuit of polynomial size。

Then the criterion for successful state preparation is that we want to prepare a state which has an inner product with the energy eigenstate that we're interested in。

 which is no smaller than one over a polynomial。In the size of the system。And sometimes。

That's hard to do sometimes we can do it and we're going to look at that problem from general perspective today。

And it turns out that sometimes we just can't solve the problem now。

I made some remarks last time about how as far as we know with quantum computers。

 it's possible to simulate efficiently any process that occurs in nature now we don't really know whether that's true or not it's a conjecture about the laws of physics。

And now we're finding that there are certain quantum problems that are just too hard for quantum computers to solve。

 so that might at first seem discouraging from the point of view of our。

Aspiration to use quantum computers to study the world of quantum physics。

But it's not necessarily so the right attitude to take， perhaps is that if there's some task。

 which is just too hard for us to perform。With a quantum computer described by our quantum circuit model that is not just hard for us and for the quantum engineers of the future。

 it is also hard for nature。 So if it's the case that preparing。

A state which has a substantial overlap with， for example。

 the ground state of some local Hamiltonian， if that's hard for us it's hard for nature as well。

 and therefore we won't expect to see systems described by such Hamiltonians in their ground states。

And so that doesn't necessarily。A obstacle to。achchieving our goal of using quantum computers to study whatever physics occurs in the natural world。

 aside from the point that the particular Hamiltonian that describes the world isn't necessarily one。

In which the ground state is hard to prepare， in fact， it's probably not。

 we have physical laws that we think describe the microscopic world like the standard model of particle physics。

And we don't think that the ground state of quantum chromatdynamics， for example。

 is a hard state to prepare either with a quantum computer or a hard task for nature somehow。

The universe figures out how to do it， at least to a good approximation， in other words， in the。

In intergalactic space to a certain approximation， what we find is something like the vacuum of quantum chromodynamics。

Okay， so I guess。I haven't started my presentation mode here， but let's do that now。Okay， so。

 but first I want to talk about the corresponding classical problem because even there。

 it turns out they're very simple looking what I'll call classical Hamiltonians for which finding the ground state is an NP hard problem。

And therefore， we don't expect to be able to solve it efficiently with either classical or quantum computers。

 and such Hamiltonians really do seem to occur in nature。嗯。And。

They occur in particular in systems that have what we call disorder systems that are sufficiently dirty。

 that the Hamiltonian can not be you know isn't spatially uniform。

 so it varies from point to point because of the dirt more or less randomly distributed in the sample and for systems like that。

 in practice they have trouble finding their ground states and correspondingly it's hard for us to find the ground state on a classical or quantum computer。

So something that we haven't discussed yet， but which we better discuss now。

Is the satisfiability problem？Which is an example of an NP complete problem。

I mentioned some examples of NP complete problems when we talked about NP completeness。

 but I only gave one example where I gave you the argument。For NP completeness。

 that was the problem circuit set， which is NP complete sort of by definition。

But a problem which is closer to the sort of problem that a physicist might encounter is the satisfiability problem where we have some set of clauses and we want to know whether there's some assignment of values to all the variables that satisfies all the clauses。

That's called a sat problem。And when I say that we're talking about a classical problem， well。

 if you like， what I mean is that all the terms in the Hamiltonian commute with one another。

You can just think of that as a problem in which the variables are bit。

Or if you want to make it sound more quantum， we could say that we can write the Hamiltonian in terms of operators that preserve the computational basis like the poly operatorator Z。

 which is diagonal。In the standard basis of the state zero and the state one。

So let me remind you about circuit Sa， well let me remind you about NP for a second。

 so the thing about NP is that if we have an appropriate witness if someone is kind enough to provide a witness。

For an instance of a problem we can。Verify efficiently once we have the witness。

 whether you know particular string is in the language or not。

 there's some polynomial size verifier circuit classical circuit when when we provide it with the instance and the witness in polynomial time it can tell us。

Whether that instanceense is accepted into the language or not。

So what I explained in a previous lecture was that any problem and P reduces to the problem circuit set。

 circuit SA is just the problem given a circuit， is there some particular input to the circuit we're given a classical description of a classical circuit？

And the question is， is there any input to the circuit which is accepted for which it outputs the answer bit one or the answer。

 yes？And if we have a magic machine thats solve circuit set。

 we can use it to find the solution to any problem in NP， that's what we mean by NP complete。

 so specifically I can consider for a particular instance。The circuit with that fixed instance。

 but with some variable witness， and I can ask。Is there any witness for which this verifier circuit accepts and circuitat answers that question。

 it tells me whether or not there is such a witness Y so that the pair x comma Y is accepted by the verifier circuit and that answers。

Whether the answer to the NP。Problem is yes or no。Now what I want to explain in a minute is a further reduction of circuit set to a satisfiability problem。

3S， I'll explain what that is， from which we conclude the threeS is also an NP complete problem。

 presumably then too hard a problem to solve efficiently in general for classical or quantum computers。

And we can think of threeS as a kind of model of a physical system。

 I'll explain a little bit more about that too。嗯。There is another problem which is NP hard。

Which involves just。Cluses that act on two variables， in the case of three set。

 the clauses act on sets of three variables。And in the case of。To SAD。

 which is finding whether a set of clauses acting on two variables have a satisfying assignment。

 that's in P， there are algorithms for solving that。But a problem which is NP hard is max2 set。

 that is if I have some set of clauses eachject on two variables I would like to ask what is the assignment that satisfies the maximal number of them。

 that is an NP hard problem and that's even closer to physics， it can be regarded as a model。Of。

A system in which the variables just interact。Pair wise and we're trying to find the lowest energy state of such a system that can be a hard problem and furthermore。

 i'm not going to give detailed arguments for this。

 but it' it's true fact that that NP hardness is preserved。

Even if the Hamiltonian is geometrically local and that's even more like physics and typically the interactions that we encounter in a physical system are geometrically local and that's true even in two spatial dimensions so the what physicists call spin glasses or disordered materials in two or three dimensions that。

Our。Reasonably well modeled by these two SA formulas。

And so we think in the case of the real spin glasses that we can study in the lab。

Those systems just won't relax to the ground state。

In an amount of time polynomial in the system size。

 so you know if we have avogadro's number of spins and a sample they'll just they'll just never find the ground state or at some non zero temperature relax to a thermal distribution so that's kind of interesting really because。

It means that we're getting some insight into physics from computational complexity。

We have some naturally occurring system that we can make in the lab。

And maybe we find experimentally that it just doesn't want to relax to equilibrium at low temperature。

 it doesn't want to relax to its ground state in particular。

 at very low temperature and we wonder why。And then we say， aha。

 it turns out that if that system could find its ground state。

 it would be solving efficiently an NP hardd problem and we don't think nature is capable of that。

 of course that too is a hypothesis， we don't think nature can solve efficiently。

 NP hardd problems and that's why these spin glasses that we study in the lab or that's a satisfying explanation for why they don't relax to their ground states。

Okay， so enough philosophy。What do I mean by the Kat problem。

 I just mean that I have a bunch of clauses。Each clause acts on it most。

K binary variables and I'm asking whether all of those clauses can be simultaneously satisfied okay is there any assignment to all of the n variables so that all of the clauses each acting on their most k variables are satisfied。

So that's what I meant here， given this formula， we say the answer to the question is yes。

If there's some assignment for which all the clauses are satisfied。

And so what I want to convince you of。Is that？We can reduce circuitat to threeat。

 so we already know circuit SA is an NP complete problem。

 so the same is true of three set if we could solve threeat efficiently。

 then we'd be able to efficiently solve any problem in NP。So specifically， what I want to say。

Is given some circuit。I'd like to find the corresponding Boolean formula。

Such that there is some input to the circuit。Which is accepted by the circuit。

 if and only if there exists some satisfying assignment for that Boolean formula。

 You want to find a Boolean formula given the circuit that has that property。

So here's what we're going to do。For each one of the gates in the circuit。

 we're going to write down a corresponding clause。And we're going to assign variables to the inputs and outputs of all the gates。

Let's say there's some gate in the circuit which has input bits X and y maps them to an output bit。

 you know this is a。Some gate in a universal set like it's an and or an ore or an Nand or something。

And what we want our clause to do is to check whether that gate is executed correctly。

So we have variables x and y for the incoming bits to the gate and z to the output gate。

 and we want that clause to evaluate to true if and only if the output is the correct output。

 given these input bits。According to the function defined by this gate， so only if Z。

Is equal to G of X， Y， if and only。Now we might also have some input bits into the circuit。

And so for each one of the input bits well consider a corresponding clause which is just going to enforce that the input bits have the right value。

 so there's some particular string which is an input to this circuit which identifies the particular instance of the problem that we're interested in solving。

 and we want each one of those bits in the string to be what it's supposed to be。

 so we put in a clause， where here the clause depends only on this variable which is output from this gate。

 it doesn't have any input and it evaluates to true only if y really is what it's supposed to be namely y is equal to x。

And then at the end， we're going to measure the answer bit to find out whether the circuit accepts or not。

And we'll put in a clause for that as well， there's some bit that we read out at the end and the circuit accepts if and only if that bit is one。

 so we'll put in a clause for that， this clause evaluates to true if and only if that answer bit is really equal to one。

ok。😊，So as I said。We can think of a formula in which all of the variables are the bits which are input and output from each one of the gates in the circuit。

We put in a clause。for each one of the gates， and if every one of the clauses evaluates to true。

 that means the circuit is valently executed， all the the inputs check。

 all the gates check and the answer checks。The number of clauses that we'll need is just going to be a polynomial an end because we're considering a circuit of polynomial size。

 okay？And。So that's really it， Okay， the witness for the threeat formula。

Is an assignment of all the variables that satisfies all the clauses。Or in other words。

 the witness is a history of the computation， it tells us at all stages of the computation what the values of the variables will be。

And。And we can easily check。That。Satisfying assignment for the three set formula。

 a check that we really have a valid history of the computation。Now we can define a sad problem。

AK set problem for any value of k where we allow the clauses to act on k variables instead of just three。

But for the reduction to circuits at。3 set is enough because we have universal gates which take two input variables to one output variable。

So to check all the gates， we only need clauses that act on three variables at once。就 the。

A witnessness is the global history of the computation that accepts an input。

And the thing is we can check that history locally。We can one at a time。

 we can look at all the locations in the circuit， all the gates， verify they were executed correctly。

 and then we know indeed that we have a satisfying assignment。

Remember one of the clauses checks that the answer bit really is one。

And now I invite you to think of our three set formula as the Hamiltonian of some physical system。

It's what I'm calling a classical Hamiltonian and it depends on。A bit variables。

So there's some number of bits and bits， the Hamiltonian is a sum of terms。

One corresponding to each clause， so the Hamiltonian depends on a its string of length and。

But it can be written as a sum of terms。Each one of these terms。Is。I guess I should have。No。

 this is fine， okay。And so each one of these terms involves only three variables。

And we choose each one of the terms in the Hamiltonian to take the value zero if the clause involving those three variables evaluates to true。

 and one， if it's false。And so the energy will be zero for the lowest energy state。

 of course this Hamiltonian is non negative， there aren't any bit strings for which its value is less than zero and it is zero only if every term in the Hamiltonian is zero。

 it's always either zero or one， every term in the Hamiltonian being zero means that all of the clauses evaluate to true。

And that's the satisfying assignment for our three set formula。So the lowest possible energy。

 the minimum for any input string of the value of the。

Hamiltonian is zero only if there is some satisfying assignment。

 the minimum is achieved by that satisfying assignment， if there is no satisfying assignment。

 then there isn't any choice of the variables for which all of the terms in the Hamiltonian or zero。

 at least one of them has to be one， so in that case the minimal energy will be at least one。

So that means that the problem of evaluating the energy for a Hamiltonian of this form two constant accuracy。

 well enough to distinguish the energy zero from the energy one， that allows us to solve3atAT。

So that means that the problem of finding the minimum energy of such a Hamiltonian is itself NP hard。

 if we could do that， we could solve three set， we could solve circuit set。

 we could solve any problem in NP。Now further things are true and i'm not going to give the arguments for this。

 I already briefly mentioned this earlier， but what physicists really do sometimes use to。

Model disordered spin systems。Is an eing spinlas Hamiltonian eing is just somebody's name。

 although some people pronounce it easing， I grew up saying eing。Um。

It's a Hamiltonian of this form now the Hamiltonian is a sum of terms which just act on two variables now I've averted to our poly operatorator notation here。

I'm considering each binary variable to take values either plus one or minus one。

 so you can think of that as like the poly operator Z that's why I wrote it as Z。And。😊。

We can imagine that we have a system on a lattice in some number of dimensions。

Two dimensions is actually enough， two or three is what we're usually interested in for experiments in the lab。

Potentially we'd be interested in things which are not geometrically local in three dimensions if we have a way of engineering a system with long range interactions among the spins。

 but let's suppose there are only local interactions on some lattice。

 let's say a two dimensional lattice。And the Hamiltonian that I want to consider looks like this。

 there are pairs of spends which are neighbors on the lattice， this means I'm summing over neighbors。

And associated with each pair， there's a term in the Hamiltonian JIJ Z I Zj JIJ can be zero in which case there isn't really a term for that particular pair。

 it can be plus one or it can be minus one。Because I put this minus sign in front when it's plus one。

 this term is happy， it has the lowest possible value when the product Z I Zj is plus one so that means the two spins agree。

 they're either both plus one or the both minus one and we say the spins line up in that case。

 and we say an edge or a pair of neighbors。For which。JIJ is positive， is Phromagnetic。

Makes the spins want to line up and phoome spins like to line up。And if JIJ is negative。

Then in order for the energy to be minimized， will1 J Z is Zj to be minus1。

So in that case the spins have opposite values， if one is plus one， the other one is minus one。

 and we call that an anti phyromagnetic coupling for that pair of spins， anti phomagnets。

 neighboring spins one to anti align。And if we have only phromagnetic couplings。

 then it's pretty easy for the system to figure out how to minimize its energy and it's easy for us too。

We would want all the spends to just line up with one another or either all be plus one or all be minus one。

 and then all these terms would be happy。But when we have anti pheroag couplings。

 things are more complicated， that can result。In。U。Frustration so for example。

 I might have three spins where each pair of the three couples to one another and spins one and two then want to disagree and two and three want to disagree but that would make two and three agree so we can't simultaneously make all of those pairs of spins happy that's what I mean by frustration。

We can compound the frustration further by adding what a physicist would call a magnetic field。

 that's just a term ZI which could take the value either plus one or minus one。

 it could also be zero in which case we would say there isn't any magnetic field at that particular site in our lattice。

 and that can also cause further frustration because a spin might want to antialign with its neighbors or line up with its neighbors according to the nearest neighbor couplings。

 but then this local magnetic field once at to point the opposite way and it doesn't know what to do。

So it turns out that in even two dimensions， if we have both these。

Peromagnetic and antiphroagnetic couplings and these local fields for the choice of JIJ and the Hs that's some instance of the problem and there will be cases where it's very hard to find the ground state energy there are many low lying states and we could try to use a kind of local relaxation model which is something like what the system in the lab would do to try to find lower energy states the trouble is that there's a very complicated energy landscape so you might get stuck in a local minimum and there isn't any way just by flipping one spin at a time to get out of that local minimum you have to strategically flip many spins at once at once to find a lower energy state and that's hard for the system to do and it's hard for us to know how to do it because there are so many different choices for how we can flip many spins at once in order to find。

One that actually lowers the energy。So it's a hard problem。嗯。The quantum version of the problem。

Is we consider terms in the Hamiltonian which don't necessarily commute with one another。

That can make it even harder。To find low energy states， there's further frustration。

 just resulting from the。Failure to commute to the different terms in the Hamiltonian so they can't be simultaneously diagonalized。

In the classical case， we can simultaneously diagonalize them。

 but there's still frustration because different terms are happy in different ways。

 in the quantum case， in a sense things are even worse because we can't even simultaneously diagonalize。

And the corresponding formal statement is that if we have a local classical Hamiltonian we're here just by local。

 I mean， that the terms in the Hamiltonian just act on some bounded number of variables。

 three in this case， finding the lowest energy state of such Hamiltonian is NP hard， so pretty hard。

In the quantum case， the corresponding problem is QM hard in general。

It's as hard as any problem in QMA， the quantum analog of NP， and we expect that that's even harder。

 so finding low energy states of quantum Hamiltonians is even harder than solving NP complete problems。

So let's try to understand in more depth why that's true。

 why is this a QMA complete problem first of all what is the problem？

So I'm going to consider a K local quantum Hamiltonian。The Hamiltonian is a sum of terms。

K local means that each one of these terms act non trivially on no more than K qubits。

And I'm going to choose each one of the terms to have a bounded operator norm。

And now the problem is this， we're given a promise。

That the lowest energy eigenstate of this Hamiltonian in each one of the terms is hermeian of course。

 so the total Hamiltonian is hermeian， the total Hamiltonian is some really big matrix。

 it can be diagonalized， it has real eigenvalues， theres some lowest energy state which has the smallest eigenvalue。

 it might be degenerate， there might be more than one state with that lowest value of the energy。

And I'm not necessarily insisting that be unique。But there's some ground state energy and I promise I'm given two numbers。

 two real numbers， I'm calling e low and E high， they're separated by some amount。

 which is no smaller than one over a polynomial in the size of the system and the promise is that the ground state energy is either less than or equal to the lower value e low。

 or it's greater than the higher value e high， or promise it's not somewhere in between。

 and the problem is to answer which is it。Is it less than or equal to e lower or is it greater than E high？

Alright。And so if we can。Efficiently with a quantum computer。

Find the ground state energy to some accuracy one over polynomial event。

 that would suffice to solve the problem。And remember， as we discussed last time。

 if we can prepare a state。Which has a overlap with the ground state。

 No less than one over polynomial event。 Then by using phase estimation。

 we can with a circuit of polyanne size。I'll find the ground state energy。So if。

Local Hamiltonian is a hard problem that means that preparing a state with a sufficiently large overlap。

 not smaller than one over polynomial event with the ground state has got to be a hard problem。

So what I want to show you is that in the case， k equals five。啊。

5ive local Hamiltonian is QMA complete。Actually， it's possible to do better than k equals5。

 but the argument for k equals 5 is easier。And this was one of Kataya's great contributions。

 by the way， to discover that the K local Hamiltonian。Is。Is a QMA complete problem？

Which he discovered sometime in the 1990s。And he his original argument established Q&A completeness for five local Hamiltonians。

That was later improved and now we know that。We can have geometrically local two local Hamiltonians。

 and it's still QM A hard， but I'm not going to show that to you today。

 We'll stick with the five local case following more or less Kahiev's original argument。

 which is also in his book。UThe the book KSV that。Is mentioned on the course webp page。

He didn't publish it as a paper， it's only in the book。

So we have to show two things to show that it's QMA complete， first of all。

 that the problem is in QMA。And secondly， that any problem in QMA reduces to five local Hamiltonian。

嗯。Well， the first part。Is maybe I forgot to say this。The first part we've already done。

To show that K local Hamiltonian is QMA， that means that there must be some witness for which we can verify the answer。

The witness is just the ground state if Merlin is so kind as to provide us with the quantum state as a witness。

 which is has the minimal energy of the local Hamiltonian。

We can measure the using phase estimation with the polynomial size circuit。

 we can measure the energy to accuracy one over any power of n that we want。

And that once we've got our estimate of the ground saving energy， we can。Check。That。

If it's we can check whether it's less than e low。If we can verify that there's some state which is energy less than elo。

 then we know the ground state energy has to be less than elo and so we can verify the yes answer。

That doesn't tell us how to verify the no answer， but that's okay for QMA。

 we just need to be able to verify the yes answer。So what we'll have to do a little work to show is that any problem in QMA reduces to five local Hamiltonian。

But the strategy we use is going to be very similar to what we use in the classical case。

Remember the。Analogously with NP。A problem in QMA has a quantum verifier circuit。

Which for a given instance， accepts some quantum witness。If and only if。嗯。That instance。

 is in the language。Okay， so what we want to do is to construct a local Hamiltonian like we did in the classical case that checks each gate in the quantum circuit。

Checks each gate of the verifier circuit for the QMA problem。And the。

The witness is going to somehow encode the whole history， the computation。

Just like that three set formula in the classical case。Encod the whole history of the computation。

And that history is something we can check locally to see that gate by gate。

 the quantum circuit was evaluated appropriately， that the evaluation was valid。

That the right quantum gates were applied。And we'll construct our Hamiltonian so that it has low energy if the verifier circuit accepts the witness with probability sufficiently high。

 greater than two thirds， although with amplification， we can imagine it's close to one。Um。

 and that there is no low energy state of that Hamiltonian if the if the witness rejects。

 if the witness is rejected rather by the verifier， no matter how we choose the witness。Okay。Um， oh。

 here's why I said it yeah， we've already shown part one， I just said that。So for part two。

 we want Merlin to help us out， Merlin is supposed to provide a quantum state。

That encodes the history of the verifier computation， which we can check locally。

So how are we going to encode the history， I'm going to do it this way。

 I'm going to consider a history state I called it Ada for some reason I can't remember。

And it has two registers this state。Oh， one keeps track of the state。Of the quantum computer。

Step by step during a computation， the other register keeps track of the time so to speak it keeps track of where we are in the computation so what the history state does if there are altogether capital t gates in the quantum computation is it's a superposition over times going from zero to capital t。

Of T in the time register tensored with the state of the quantum computer。

At that time when we execute the circuit， so in other words。

 what I mean by psi of t is there some input， which is the witness to the QMA complete problem。

And then the gates supplied by the circuit are U1， U2， U3 and so on and sequence。

 so when I've gotten up to time T， the unitary that's been applied to the input witness is this product first U1。

 then U2be， blah， blah， blah up to UT。So we can think of this register as the clock。

 it keeps track of where we are and the evaluation of the circuit。

 keeps track of what step we're at what time it is， so to speak。

And so now our local Hamiltonian is going to be constructed so that。

History states which have valid input and get a yes answer in the output for which all of the gates are the correct gates specified by this quantum circuit。

 we want those to have low energy and we want states where the witness gets rejected or where the quantum circuit was not validly executed to have high energy。

And we want to do that with a local Hamiltonian， and it's going to be a sum of four terms。

I'm calling them H in H out， H prop and H clock。So what HN does is it checks that any input bits that we're going to use for scratch。

 which let's say are supposed to be initialized to computational basis state zero。

 that all of those are correctly initialized， so it will penalize a state in which those initial input bits are one instead of zero。

H out is the term that's going to check the answer。

And we want the when we measure the output bit at the end to be in the state one。

 so what H out is supposed to do is to penalize states in which that final answer bit is zero。

And HC will come to later， if we have to encode the time in an appropriate way so that our Hamiltonian will be local and what H clock will do is it will impose a penalty。

If the encoding of the clock is not properly done。And then there's going to be a term which I call H Pro。

meaning it propagates the state along step by step。

 and the job of H Pro is to enforce that at each time we're applying the right gate， in other words。

 it should impose a penalty if the gate that we apply at a particular step of the computation is not the right gate。

So in order to get a low energy state of the Hamiltonian。Everything has to be done properly。

 we execute the right quantum circuit with the input bits fixed correctly。

 we wind up with one in the answer bit， at least with high probability when we measure it。

And thanks stage Pro， all the gates in the computation are the correct ones。

For the circuit of interest。Which we imagine is the verifier circuit for some。QMA problem。

 some particular instance of it， acting on the witness that Merlin provides。

So let's talk about H prop。So here's I've just rewritten the history state again to remind you what it looks like。

Where。Coherently superposing。Over all of the times。At each time。

 that's correlated with the state of the quantum computer at that particular time。

Different times in the time register are orthogonal states。

So each one of these states has norm one and they're orthoormal because the times are different。

To normalize it then I just divide by the total number of different times represented here。

 including times zero， so that's altogether capital t plus1 times and so the state as I've written it here is normalized to one。

Pi of T again， is the particular sequence of gates that have been applied up to time little T。

Acting on our input witness。So I want H Pro to do the job that if we apply use of T at time T like we're supposed to。

Each prop will have zero energy。Okay。And here's how I'm going to choose it。

 it's going to be a sum of terms。A term for each time。

And the term for time T is going to look like this。It has。A term that projects the time onto T。

 another term that projects the time onto time t minus1。

And then there are these terms which change the time this maps the time on the clock t minus1 to time t。

 and as it does so， it applies the unitary UT and I put this in with a minus sign。

And then I also have its hermeian conjugate， of course。

 the Hamiltonians got to be Hermeian these terms are。Real and diagonal their hermeian。

 this one isn't so I have its ammeian conjugate as well and what that does is it evolves the state backward in time。

It takes the state of the clock t to the next earliest time t minus1 and as it does so it applies the inversesive use of T。

ok。Or it's adjuint。And so now we can ask。Once we've reached state state t minus1 or state t。

Of the computation， what does HPPro do？To one of these states in the superposition。

 like psi of t minus1 tensored with clock time t minus1。Well， this particular term。

Is going to act only。With this guy and this guy， because the time T here and here is orthogonal to t 1。

It，This term just projects out that the time and doesn't act on the state。

 so it leaves the state alone psi of t minus1 tensor t minus1。But this guy。

 it advances the clock from time t minus1 to time t and as it does so。It applies U sub T。

 So what that does is it advances the state from a psi of t minus1 to a psi of T like it's supposed to。

But I can also consider the action of this H prop。On。The psi of t tensor T。Part of the superposition。

So now the terms that are going to not annihilate the state。Are this one。

 which is just the identity acting on this day？And that gives our rise to this term。

 and this one which makes the time go backwards from t to t minus1 and applies a UT ad joint。And。

So look at what we got here， this U T a joint is going to makesi of t go to psi of t minus1。

 It takes a step back in the circuit。Luckily， our unitary gates are all reversible so we can take steps backward。

 just like we can take steps forward。And I put in these minus signs now， you can see why。

This state is psi of t minus1， tens or t minus1， this state is also psi of t minus1， tensor t minus1。

Because like I said， Ut a joint takes psi of t to psi of t minus1， so these two cancel one another。

And here we have this psi of t tensor t， and this state is also psi of t tensor t because Ut takes psi of t minus1 to psi of t。

 so these two also cancel one another。Okay。So you can go through how the terms in the Hamiltonian act on all the terms in the superposition。

And you can see that H PR defined this way， in fact， annihilates every term in the superposition。

 we always get these cancellations。And so that means when we have the valid history state。H prop。

Is going to be equal to 0。And in fact。That's its lowest energy state。

We can actually find the whole spectrum of HP PR and so in particular I'd like to know。

What is the gap between the energy of the lowest energy eigenstate of H Pro and its first excited state？

But we'll do better than that， we can completely diagonalize each prop。

 turns out not to be that hard。And in fact， to make that convenient to make it easy。

 we can make a change of basis by diagonalizing H prop by a particular unitary to make it especially clear how to diagonalize it。

 Now， if we conjugate。H by a unitary， that doesn't change its spectrum。

 that doesn't change the eigenvalues of H prop， it only changes the eigenstate corresponding to each one of the eigenvalues。

what I do is I consider V。Which。At time T applies the appropriate unitary evaluated by the circuit up to time T。

Namely the product use of T use of t minus one， blah， blah， blah u1。

I sum that overall possible values of the clock。And what that does is it removes the use of teas essentially we've gone to what。

Sometimes we call the moving frame now we're looking at the state from a point of view that rotates as the clock advances and so because of the rotation。

The state doesn't seem to change with time at all。Because every time we advance the time。

 we're choosing a reference frame which has that extra use of T multiplying it。

So the multiplication by u sub T becomes just the identity in that rotating frame and we that means we can get rid of the u's。

In the。And you prop。And so。Now it's simpler， we have the terms which are diagonal in the time。

And we have these propagation terms with change the time。

Advanced time t minus1 to T and its remissionian conjugate， which goes backwards。

 takes time T back to time t minus1。And now we have to diagonalize this matrix。And。

That's something that we can do capital T is going to be polynomial in N。And so。Actually。

 this is a problem which I explained in detail in the notes。

 but I'm not going to go through it in class。How you do the diagonalization。

 but essentially the idea is to Fourier transform。To this is。Sort of a translation invari in time。

Hamiltonian， except that it has endpoints。At time zero and time capital T。

 but in the middle of the chain of times。It looks the same at each time。

 so the way to diagonalize it is to consider。A state which has a definite frequency。

In which the time T occurs with a coefficient， which goes like e to the i omega T。For some omega。

And if it weren't for the boundary terms， if it weren't for the fact that we have boundary conditions at little t equals0 and little t equals capital t。

That would that would diagonalize。H prop。But then because of the boundary conditions。

 there are only special values of mega。Which are allowed and in the notes I worked out what those special values are。

It turns out that if you ignore the boundary conditions。

 the positive frequency and negative frequency have the same eigenvalues for HP。

 and so we can put together e to the i omega T and e to the minus i omega T。To get an niigen state。

 or in other words， we can choose the coefficients to be a cosine。Of omega t plus a constant。And。

To handle the boundary conditions right， you have to choose omega K to have special values。

Which are just integer multiples of pi overt capital T plus1。

 and you can find the corresponding eigenvalues。Of these energy eigenstates。

 which are just two sine squared omega k。So like I said， there are details in the notes。

 but this problem is actually mathematically identical to a problem you might have encountered in a physics class。

Namely， the problem of finding the normal modes of a chain of oscillators。

 a chain of masses connected by springs for example。

 where all the masses are the same and all the strings have the same。The same spring constant。

But with boundary conditions。Holding the masses at the ends fixed。

And it's the same problem mathematically and it's not too hard to solve。

 though I went through a page or so of algebra to do it in the notes which I'm not going to reproduce here。

But at any rate， what we're especially interested in is the difference between the energy of the ground state。

 which is zero。That's just the omega equals zero case here where this energy is zero。

 and then the first excited state is when omega has the lowest possible value up pi over t plus1。

And so the difference between the energy of the first excited state in the ground state is two sine squared pi over2 t plus1。

And if t is a big number， let's say polynomial and n where n is a large input size。

Then that's approximately。Pi squared over2 t plus1 squared。In other words。

 I just do the approximation to the s， sine x， approximately the x。

Square that multiplied by two and I've got this。 So if since the the circuit that we're considering has polynomial size。

That's a splitting， which goes like one over a polynomial event。Okay。So。There's one more thing。

We have to make sure that we get the right answer。I haven't said explicitly what the H out term is in the Hamiltonian。

That'll be something like this we wanted to penalize the answer bit if at the final time capital t the output bit has the value zero instead of one。

We're interested in the case where the witness is accepted， where when we measure the output bit。

 we get the value1， so what H out does is it just looks at the final time on the clock capital T and it penalizes the output bit being zero instead of one。

ok啦。So let's say that。We consider a verifier circuit that accepts with a probability close to one。

One minus epsilon。Then。If we consider a valid circuit that H Pro will be happy。

 if the input bits are set up properly HN will be happy， I'll assume the clock is properly encoded。

 which means H clock is also happy， so the only term that might not be completely happy is the H out term。

And so the only contribution for that state corresponding to the valident history state to the expectation value the Hamiltonian comes from H out。

That contribution occurs only when the clock is capital t because H out projects onto capital t。

 so in this superposition it's only the term with the time equal capital T。That matters。

And then if we get the value zero with probability epsilon instead of the value one。

Then the expectation value of H out will be epsilon over T plus one。So there is a state。

 namely the valid history state。Whi has an expectation value of the full Hamiltonian epsilon over t plus1。

 so there must be so we the ground state energy can't be higher than that。

 it has to be less than or equal to epsilon over t plus1。That T plus one is a little bit annoying。

 actually there's a way to get rid of it。So that this actually becomes epsilon times some constant instead the trick for doing that is that we can add extra steps to the computation in which nothing happens。

 so the clock continues advancing up to sometime like say capital T times two。And。

But during those additional time steps， there are no additional unitaries。嗯。Applied。And。

So the output bit isn't changing at all。And then we could have our H out project not just on time capital T。

 but have terms projecting on to later times as well， capital t plus one， capital t plus2 and so on。

And so if you measure at any one of those times， you'll get the same answer。So。You'll get。

A expectation value for each one of those terms， epsilon over t plus one。

 but theyre order capital T of them。So that makes the。

Then the conclusion is the expectation value is actually epsilon。嗯。And。Well。

 it doesn't really matter， but the t plus one is doesn't necessarily have to be there。

 I guess is the point now there's another thing which is I can imagine we make epsilon small by amplifying remember in the in the definition of QM。

U。We assume that。You know， if something's in the language。

 we we accept with probability at least two third， just like in the the case of。BPP。

But I can have multiple copies of the witness and check them all and I can make the make that probability very close to one now that's a little bit tricky because we don't necessarily trust melin and he won't necessarily give us。

A when we ask for multiple copies of the witness， a tensor product of the different copies。

 he might try to give us some entangled state entangled across the copies。

 but we can still amplify because if we look at each one of those copies one by one tracing out the other copies。

You know， if each copy gets accepted with probability2 thirds， then。

Then we'll still be able to amplify and I won't explain that in detail。

 but at any rate you can amplify and you can make epsilon exponentially small with a polynomial number of runs or a polynomial number of copies of the witness as usual。

Okay， so now。So let's imagine Epsilon's really small， as small as we need it to be。

Now what's our Hamilton and I'm still going to ignore H clock I'm going I suppose we we make each clock happy by validly encloing the clock I haven't told you what each clock is yet。

 I'm going to come to that next。But before we get to that。嗯。

We're just considering HN plus H out plus H Pro。I'm going to call that H1 plus H2。

 I'm going to separate the H in plus H out term which checks our input scratch bits and checks the answer。

 call that H1 and then H2 is the propagating part which advances the time。

These are two non negative operators， they both have states with zero eigenvalue what I'm calling null vectorctors。

 states that they annihilate。So in the case of H2， that is H Pro， as we've seen。

It annihilates a state in which all the steps in the computation are valid。In the case of H1。

 that is H in in plus H out， it annihiillateates a state in which the。

Answer bit is one and the input scratch bits are。Properly prepared， all in the state zero， say。

But the。Nll vectors for H1 and H2 are not the same necessarily， in fact， if epsilon is nonzero。

 they're not the same because when we have a valid history， we don't always get H1。

 so the valid history state is one in which the expectation value of H1。Is positive。And likewise。

 the state in which H1。嗯。Is has expectation value zero， the output bit is exactly one。

 and then we won't have a valid history state。So we have these two， we have a Hamiltonian。

 which is sum of two terms。Each one of them has a null vector， each one of them has a gap。

Between its。呃。Nll vector and which has eigenvalue zero and the next highest eigenvalue。

In the case of H1， the gap is just one。Because。You know the next eigenstate is one in which one of the input bits or the answer bit has the wrong value and that's going to cost one in energy in the case of H2 we've already said what the gap is。

Because we diagonalized each prompt and so that gap is this guy essentially a constant over T plus one squared。

Um。And。So'm there's an argument in the notes which gets a little involved and I'm not going to go through it。

 but you can believe that from the information that we have H1 and H2。Have no vectors。And。

When we consider the state， which is a null vector of H2。

 H1 has this expectation value epsilon over t plus1 rather than zero。

We know the gap for H1 and we know the gap for H2 and that's enough for us to get。

A lower bound on the expectation value of H1 plus H2 in any state。

And here I've just written down the answer， I'm not going to go through the argument。

 though there are details in the notes。And the important thing。

Is that well we wind up getting an answer that depends on this epsilon and also on this gap。

 so this is the dependence on that gap coming in， this is the dependence on epsilon and we wind up with something like one minus the square root of epsilon over。

T plus1 Q two powers of t plus one coming from this gap， one power of t plus one coming from this。

This bound on the energy for valid history states， which， as I said， we could get rid of。

By modifying the circuit a little bit。The important thing is。That we have this expression。

For the energy。And。We have this expression， actually there are two different epsilons here。

 I should apologize for that， I guess。So here I'm talking about the case where the acceptance probability is one minus epsilon。

And then we know that there have to be states。With an energy for this Hamiltonian。

 which are less than epsilon over t plus1。So in the case where we accept with high probability。

 energy very close to zero。Here I'm considering the case where the eilon。

 the acceptance probability is epsilon。Not one minus epsilon。

So I'm interested in the rejection case where we accept with small probability now。

 so that means this epsilon is small。And so this is essentially one over some polynomial and N。

 that polynomial being determined by the size of the circuit。

So once we've made epsilon smaller than some power by amplification。

We have a separation between the case where the verifier accepts and the case where the verifier rejects。

And so we can make the energy in the case of acceptance smaller than the energy in the case of rejection by some one over polynomial n factor。

ok。So that's the reduction that we wanted， it means that。

You know if we can solve the local Hamiltonian problem。If we can say for this Hamiltonian。

HN plus H out plus H Pro plus H clock。Whether its lowest energy state has energy less than or equal to e low or energy greater than E high。

We can answer the question of whether a witness is accepted or rejected。

And that's the idea of how we can use the solution。To the local Hamiltonian problem。

To solve any problem in QMA。Okay。Except there's one thing we haven't explained yet。

And that's how we encode the clock。And this part's a little tricky because we want to be sure that it's an encoding such that。

The Hamiltonian will be local。And there are different ways to do this。

 but I'm going to explain the simplest one， it's kind of a dumb way of encoding the clock。嗯。

But it works。I call it a unary encoding by which I mean we're actually going to， you know。

If I represented the time and binary。Then I would only need log capital T。Hubbit。

To encode capital T different possible times， but I'm actually going to use。Capital Tbits。

To encode T times。 In other words， I'm not going to allow all binary strings， just special ones。

Time zero is all zeros， time1 means one in the first place， the rest zero， time two means1。

1 in the first two places， the rest zeros， time three， 111， followed by zeros and so on。

So I'm only considering strings。Which start with some sequence of ones。

And then the rest of the bits are 0。 and it's the location of the。Domain wall， so to speak。

The transition from1 to zero， which encodes the time。If I only want the clock to be to have states。

Of that form， if all other states of the clock are to be invalid。

I want to penalize those in balance states。Well， it's enough。

To penalize the case where one follows a zero。For these valid stock clock states。

It's okay for a 0 to follow a 0 and for a one to follow a1 and for a0 to follow a 1。

 But it's forbidden for a one to follow a 0。 Once I've made the switch over from  one to 0。

 I can never go back to one again。And so to enforce that。

 it's enough to write down a local Hamiltonian which penalizes invalid clock states and what it has to do is for each pair。

Of indices。Where these indices run from1 to capital T。

 indicating the location in this sequence of capital T bids。I penalize a pair of。

Adjacent bits in the string being 01。00 is okay，1，1 is okay，10 is okay，01 is penalized。

And so then the only states of the clock which have zero energy are going to be these valid states。

Now in our HP part of the Hamiltonian。We had terms that project onto a particular time。

And we have terms that advance the time， and we have the Hermeian conjugate terms which retiredard the time。

So now we need to be able to write down those terms in a way which is local。

 which just acts on a constant number。Of qubits。But once we've enforced the valid。Clock and coding。

It's enough to project onto to a particular time。To project onto to two。

Successive bits having the value 10。Okay， so if I know that the indices labeled by。

One or 10 then I know the time is t。Well， actually， I guess if I want to check time zero。

Then I would just have to check that the first bit is zero。

 but for all later times this two local operator does the job and for time zero it's actually just a one local operator it just looks at the first bit to see whether it's zero over one。

If it's  zero， that's time zero。And。So likewise， unless we're talking about time zero time capital T。

If I want to advance the time from t minus1 to T， now I can look at three bits in succession。

And if I see 100 to advance the time， I replace that by 110。And if I want to retiret the time。呃。

If I see for a particular three bits， the state 110。

 then I know the time is the one corresponding to the domain wall here between one and0。

 and I move the domain wall a one step to the left。To change to the earlier time。

This had to act on three bits instead of just two， because if I changed 11 to 01 that might be changing the11s know to the left of the domain wall。

 I want to be sure I'm really at the location of the domain wall so that this one is followed by a zero before I'm going to be willing to flip this one and in move the domain wall one step to the left。

So these are three local operators。ok。And therefore。

If I have a set of universal gates where all the gates in the set act on a pair of qubits and we know there are such universal gate sets。

Then my H prop will be five local。Because we have terms that。

Add an additional gate in the register for the quantum computer。And advance the time。

In the clock register and the Hermeian conjugate of these which apply UTA joint and retard the time and these act on five qubits because the clock part of the Hamiltonian acts on three qubits of the clock。

And then we also have。The unitary that changes the state of the quantum computer。

 which acts on a pair。So now we've got it to Hamilton and SHN。HN plus H out plus H Pro plus H clock。

All the terms are five local。And。If we can estimate the energy of this Hamiltonian to one over pollan accuracy。

 we can check。Whether the witness is accepted or not。And that's enough to solve problems in QMA。And。

That means it's going to be a Q andA hard problem。To find the ground state energy to that accuracy。

 and as I've already remarked。As since once we prepared the ground state or a state that overlaps sufficiently with it。

 we can use phase estimation to measure the energy， so that means preparing ground states。

Has got to be hard in general， A Qa may hard。Now， we haven't paid any attention to geometric locality here。

I haven't worried about how the clock qubits are laid out。

Relative to the qubits of the quantum computer。Now it is possible to strengthen the argument。

So that we can make everything geometrically local that requires a different way of encoding the clock。

 I have to encode it in a more distributed way so that each one of the gates I want to perform in the quantum computer can just look locally around to see what time it is on the clock and there there are ways of doing that。

It turns out。And。In fact， we can reduce the。Um。K locality。

 we can reduce K further all the way down to to local。With qubits。They'm not explaining the details。

 but it's a true fact。That it's already Q M A hard。To find the ground state energy。

For in two dimensions。A two local。Hamiltonian， where we have a lattice of qubits and the Hamiltonian is a sum of terms acting on pairs of neighboring qubits。

In a two dimensional lattice。And if we're willing to go beyond qubits and consider higher dimensional systems。

I'm not sure what the current record is， but systems which have。嗯。

A local dimension of 12 is good enough。I wish we can encode with four qubits， for example。

So if we have a chain in one dimension。Of D dimensional systems where D is 12 or greater。

 the problem of finding the ground state energy of such a Hamiltonian。Is Q&A hard in general？

So you can think of that if you like as an encoding with qubits。

Where the terms in the Hamiltonian can act on in the chain。Neighboing qubits。I guess act on。

 let's say， eight qubits which are adjacent in the chain。

With four of them encoding one D dimensional system and four of them encoding another D dimensional system where。

um。D is。Well could be 16， but I guess 12 is enough。And that was a surprise。

 certainly a surprise to me we already knew in the case of。The classical case。That too local。

Spin glasses。In two dimensions。A and Phard to find the minimum energy。

And so it wasn't that big a shock。To find that there's a comparable statement for quantum systems on a two dimensional lattice。

Or we have qubits and a two local Hamiltonian， it's QMA hard。To minimize the energy。

But in the classical case， one dimensional spin chains are easy。To find the minimum energy。

But in the quantum case， because of the non commutivity of terms in the Hamiltonian。

 we can frustrate even a one dimensional system。And it can be very hard to find the ground state energy and it's it's turned out the one can go。

Even further in a certain direction， another result， which。Is fascinating and somewhat surprising。

Is that we can ask about the problem of estimating the energy gap。

Asymptically as the system size gets larger， you know， whenever we talk about QMA or NP。

 we're considering。A language， so we have problems with variable input size。But let's say。

That we have a。Hamiltonian， that's translation and variant。

Except maybe for some boundary conditions at the end。

 so we can imagine a one dimensional chain of D dimensionsal systems。

Where the Hamiltonian is a sum of terms acting on。Pairs。Of adjacent D dimensional systems。

On the chain。But different terms in the Hamiltonian don't commute with one another。

Because they have in common one of the systems that。That they act on， in other words。

 if you act on one Hamiltonian acts on。Dimmenional systems labeled six and seven。

 another one x on7 and eight， and those terms don't commute with one another。

You can ask about how the energy gap。The gap between the groundside energy and the first excited state behaves as the size of the system。

Ha goes to infinity。Translation andvari system except for the boundary conditions。

So the Hamiltonian has a fixed form and the only variable now is the system size。

And the yes or no question that we're interested in。Is does that gap asymptotically go to zero？Or。

Does it remain a non zero constant in the limit of infinite size？

So physicists say is the system gapless or not， we say it's gapless if the energy gap goes to zero。

 that is gapped。If the gap between。Lowest energy and first excited state。

Is above a non zero constant， even as the system size goes to infinity。

And it turns out this is an undecidable problem。Okay。

 it's always possible to encounter a surprise as you go to larger and larger systems。

 you might think， oh， it's gapless， it's gapless， it's gapless。

 and then suddenly you find no it's not when the system size， of course。

 you don't really know it's gapless until you get to infinite size because it's a statement about infinite size。

But the point is that for arbitrarily large system size， this is why it's undecidable。

 there can be a kind of abrupt changeover from what looks like an energy gap that's going to zero to one that's not or vice versa。

And so。It's kind of a remarkable thing about what seems to be a somewhat natural a manybody physics problem。

 not only is it computationally hard to solve， it's actually undecidable to solve whether the system is gapless or not。

 although admittedly。One has has to be rather clever in designing the local Hamiltonians that have this undecidable property。

 and might they might not be ones that would occur naturally occurring systems。

 but you know we really， we should be broadening our view about what's naturally occurring。

As quantum engineering advances because systems that you might not find out in the field when you pick up a rock are ones that will increasingly be able to realize with our quantum devices so those have become part of physics as well and we can say the same about geometric nonlocity geometric locality is natural because usually physics is local。

 only systems that are near one another interact substantially。But it's possible to engineer systems。

Wwhich have geometrically non local interactions， and we can study them in the lab and investigate their properties。

 so that's part of physics as well。So we've come to the end。

There's a lot we haven't covered this is the last course of the term。

You will continue if you're so inclined next term with Professor Katya。And what he does in。

His part of the course is up to him， I expect though， that he will。

Address the issue of quantum error correction and how to protect quantum computers against noise。

 which is also a very remarkable。Development in the subject， I think， of course。

 what we focused on in recent lectures is that quantum computers can solve problems we think are too hard to solve classically。

 and that is a fascinating and amazing thing that。There's a difference between classical and。

Quantum worlds as far as what are the hard problems is concerned。

But I think another discovery dating back to the 1990s， which is of comparable importance。

 is the discovery of quantum error correction that despite the prevalence of，Of decoherence。

 despite the noise that quantum systems are subject to。

 we can with reasonable resources in principle， make them behave we consider。

Quantum systems of asymptotically large size， we can control them using the principles of quantum error correction and in particular。

We can make a noisy quantum computer behave like an ideal quantum computer with a reasonable resource cost。

To a remarkable extent， by the way。Shiining results in the whole field of quantum computing are due to Professor Kaya。

 so it will be a privilege for those of you who choose to take advantage of it to hear from him。

His wisdom about the subject。So much of it we owe to him。And his very creative contributions。

There's a lot I haven't covered， some of which he will cover， but some of which he will not。

We actually have a course now on quantum cryptography。

 which has been taught a couple of times by Thomas Fity not being offered this term。

Pa Thomas is on leave。Enjoying himself in Paris， teaching a special topics course there actually。

 which is online。And I'm sure it wass very interesting。But at any rate。

 quantum cryptography is a fascinating topic， I made a few oblique references to it。

It's based on the idea。That we can't。Observe quantum systems without disturbing them in some detectable way。

And that makes it possible to design protocols whose security is founded on principles of quantum physics rather than computational assumptions。

 like in the case of RSA， I explained how the security of RSA was upended by the discovery of Shore's algorithm。

There's an alternative approach to protecting our privacy based on quantum communication。And。

We have a course on that， which is offered from time to time another thing we haven't talked about in this class is the hardware。

I made a few occasional references to it， but how do you actually do this stuff。

 how do you build quantum devices， a fascinating and rapidly evolving subject for which we have course。

 which however， isn't being offered this year on quantum hardware and techniques。Of course。

 sometimes we have special topics courses on。Quantum topics。

And one which has been offered in the past and I think will be again in the future。

 it was taught by Austin Minch last year。Was specifically about near term quantum computers because that of course is also an aspect of the subject which is rapidly evolving there are quantum computers now admittedly small ones with limited power。

That one can access through cloud interfaces that will be increasingly true and Austin Minch taught a course。

Focused on the things we can do or hope to do with near term quantum computers and simulating what they do and actually running quantum computations on real platforms。

It's very important。 And at this stage， pivotal。Question。

Can we do things with these near term noisy quantum computers before we have enough physical qubits to implement full blown air correction。

 Can we run interesting applications on them， That's still an open question and an important one to address in the next couple of years。

 We actually now have a quantum science and engineering minor， which is just。Getting underway。

 I didn't actually know until this。Was introduced that it's possible to have a minor in a PhD program。

 but it is。By taking a few courses， including this one。That is 219。You can qualify for。

This QSE minor and something that would go on your PhD diploma。Of。

And at least if you were trying to convince a prospective employer that you've been trained in quantum science and engineering。

 this would be a way of providing documentation for this。

I've been teaching a course on quantum computing for a while， so is Kahiev。

For the first time in 1997-98， a number of times since then。And the topic has evolved。

 and the course has evolved to some degree。The material that we covered in this term。

Was mostly known。And already。Back in the 90s。I still consider it to be an essential part of the quantum knowledge that someone interested in pursuing research in this field。

I should know。U。I mean， there's a lot more that could have been said about quantum algorithms。

 of course。A lot has been discovered about them。In the last 20 years， but I think。

What we took the time to cover understanding phase estimation and period finding and applications to。

Quantum problems are still among the most important things to know Grover's algorithm as well。

 So I think you've seen a lot of the essentials， as you saw。

 we spent a lot of time on some of that background material at the beginning that wasn't completely necessary。

 I could have talked about quantum algorithms without going into quite so much detail。

On density operators。And quantum channels。But I consider that also to be。Essential。For up。

More advanced investigations or study。Of the topic and I also think it's pretty interesting material that usually isn't covered。

In physics classes on quantum mechanics， but in the arena of quantum information is。Is quite。

Is quite essential。So that brings the course to a close， I appreciate。Your loyal attendance。

To these lectures。Even though I can't see you， I know you're out there and it's been a pleasure having the opportunity to share this topic with you。

 it's certainly a fascinating one， it's a rapidly developing and growing field of science and technology and I expect that will continue。

For some years to come， and I hope some of what you learned in this course。

 you will carry with you in your future endeavors。So that's it。

I guess I don't have to say see you next time， although I'm sure I'll see you around at some stage in the future when human beings come into physical contact。

With one another again， and you know， if you happen to see me crossing the campus when that。

When the coronavirus era has。Has reached its termination。

 I might not know you because I didn't see you when I was teaching the class。

 but come up and say hello and say， hey， I took your course。And it was okay。Or just say hello。

 and you may know me， but I might not know you and of course that's one of the regrets。That in this。

In this era。It wasn't possible for us to have that direct contact。But anyway。

 please take care of yourselves， be careful， stay healthy。And I。



![](img/759709973aad70be5d452e3ad1924356_2.png)

Well， hope to see you someday。Okay， bye bye。