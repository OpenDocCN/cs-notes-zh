# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p23 -23-Classical Shadows of Quantum States _ Quantum Colloquium.zh_en -BV1KgffBoEUc_p23-

Hes， of course， he needs no introduction， he's one of the giants of the field。So John is a theorist。

 but I think his work has reached out in many ways to both the foundations of physics as well as to more practical quantum computing。

 between his work and correction and quantum gravity and N devices and so obviously today is probably reaching out more towards the practical side I should say one thing that's really remarkable by John is that I think an astounding fraction of the people in the field。

 especially on the physics side， have been mentored by him， so John looking forward to your talk。

Alright， thank you， Umesh for the。The kind introduction。

I guess I can't resist mentioning that an astonishing fraction of people in the field on the computer science side have been mentored by you。

嗯。I'm going to。Talk mostly about。Some work I've done with Robert Juan and Richard Cohn。

My collaborators are far more knowledgeable than I am about machine learning and probability theory。

 this has been a very illuminating and exciting collaboration for me。

And in the second half of the talk， I'll say some things about some work we're currently doing joined by Victor Albert and Jacomo Torla。

So the theme is classical shadows of quantum state。

 so what does that mean and why should we care about it？

But what I want to describe is an efficient and experimentally feasible way。

Of translating a quantum many body state into succinct classical language while retaining。With that。

 classical description， the ability to predict many useful properties of the state。Whats that useful。

 where in the NSC era。We are aspiring to achieve quantum advantage。In platforms。

 perhaps in the next few years。And perhaps our best hope for doing so is by means of hybrid quantum classical algorithms to use our classical computers to the extent that we can and then boost their power with。

Quantum devices used as co processorors。So if it's experimentally feasible to trade quantum for classical resources while not compromising our ability to carry out an application。

It's likely to be beneficial to do so。And with these classical shadows。

 we can improve the efficiency of variational methods for solving optimization problems。

 and by converting from quantum to classical language。

 we can then use classical machine learning tools。To address quantum problems。

So what we're shooting for？Is some tractable way of translating from quantum to classical data specifically we would like。

If we have a。Quantum mini body state in our quantum device to be able with a small number of measurements which are easy to do experimentally to obtain this classical description from which we can predict many properties of the many body state。

We want that classical description to be succinct and easy to store and we want our predictions to be easy to do by classical computation。

 and we want a rigorous guarantee that our predictions have a small error with high probability。

The kinds of properties we might want to predict are fidelity with target states。

Or expectation values of a local observables or few point correlation functions or entanglement entropy。

And the types of resources we'll care about is how difficult is it to do this translation from quantum to classical on our quantum platform？

How many copies of the quantum state will we need to be able to make accurate predictions？

How much classical memory we'll need and how much classical processing to derive those predictions。

So as you know。There is a procedure for translating a quantum state into classical language。

 doing full quantum state tomography。And then we can use that classical description to derive properties of the quantum state。

But full quantum state tomography is very inefficient for many body systems。

The description itself is exponential in the number of qubits， the system size。

 the number of samples that we need to extract accurate predictions is also exponential in system size。

The amount of classical storage and classical processing we need to do to compute predictions is also exponential。

 So that's not a practical procedure for。Systems with manyqubits。

There is the ingenious idea of shadow tomography。Which Scott developed and analyzed where one doesn't try to learn a complete description of the quantum state。

 but the goal instead is to make accurate predictions for expectation values of some set of operators。

And remarkably， in that case， it turns out the number of samples that we need to make those predictions scales polynomially with the system size。

 and furthermore， in order to predict M properties。

 we only need a polyloarithmic number of copies of the state。However。

 this is still not a practical procedure because it requires very expensive quantum processing。

 including quantum computations that。Ac across multiple copies of the state。

And a lot of storage and post processing to make predictions。There are also heuristic ideas。

For extracting predictions from quantum states like neural network， quantum state tomography。

 one can perform some set of measurements to train a neural network。

 which can then be used to predict additional properties of the state。 and in practice that。

May work well in some instances。 And furthermore， the quantum experiments that we need to do to train the neural network are feasible。

But we don't really have a rigorous theory of neural network quantum state tomography。

 its sophuristic procedure， and so we can't say in general， for some input quantum state。

 how many samples we'll need， how much storage and how much processing in order to get good predictions with high success probability。

So what we'd want is。A procedure where we can prove that it's efficient both in terms of the quantum processing we need to do on the input state。

 the amount of classical storage we need and the amount of classical processing we need。

Which will enable us to learn some classical representation of。An unknown input state。

From a small number of measurements， and then use it。To predict many properties of the state。

And the result that we proved about a year ago shows that this is possible under certain conditions。

That if we want to predict expectation values of a list of observables and to do so with a small constant error with a high success probability。

Then the number of copies of the state that we need to do。

 the number of repetitions of the experiment。Is just logarithmic in the number of properties to be predicted。

But there's a catch。There's a prefactor here， which depends on something I've called the shadow norm and we require all of the operators to have a sufficiently small shadow norm。

 I'll explain what I mean by the shadow norm later on， but it turns out for。

Some cases of interest that the shadow norm is actually a constant independent of system size。

 so in that case we're saying that we can predict m properties with the border logm measurements and the sample complexity that we need。

Doesn't depend on the system size at all。 The experiments are。Efficient。

On the quantum platform and the classical storage and processing are also reasonable。

If I wanted to just naively， measure M different observables one by one。

I would need a number of copies of the state and the millions。

 but we're saying that we only need a few times the log of them。

Copies of the state to get accurate predictions with high success probability a big improvement。

So let's see how this procedure works。Let's say we have n copies of the state and so we repeatedly do experiments on the state in the following way。

 there are a number of variants on the procedure， but they all have in common that it's a randomized protocol。

And there's some ensemble of unitaries that we can choose from。And in each run of the experiment。

 we select a unitary from that ensemble。We want this unitary to be something we can really do in the lab。

 and we also want it to be something that we can describe succinctly in terms of classical data。

We apply that unitary to the system and then we measure in the computational basis if it's an ncubbit state。

 we collect n bits of data in doing so， and then we obtain a snapshot of the state。

 which is the result of applying the inverse of the unitary to that measurement outcome and this is something that I do。

Acting on the classical data， the unitary is something I can efficiently describe and invert。

 and so I can apply that unitary to the bid string to get this snapshot and the full collection of all and snapshots is what I'm calling the classical shadow。

So let's note for later reference that if I consider averaging over all the unitaries in the ensemble and also averaging over the measurement outcomes that defines some channel acting on the input quantum state。

 some CPptTP map。So again， what we were going to want to do is we have this very complex。

Quantum beast in the lab。And what we do with it time after time is we apply some unitary chosen from our ensemble and then we do computational basis measurement that gives us a snapshot and then we do it again and again。

 and that collection of snapshots is the classical shadow。So to make it even more。Concrete。

Let's suppose， for example， that I have some quantum state which lives on the equator of the B spheree。

And our ensemble of unitaries is the identity and a 90 degree rotation about the Z axis of the B spheree。

So depending on that choice of unitary， I'm either measuring in the computational basis zero on1 or in the x basis plus or minus。

And for this particular state，m when I measure in the Z basis， I'm more likely to get a zero。

 the less likely to get a one。If I measuring in the x basis， I'm more likely to get a plus。

 less likely to get a minus。But the snapshots are zero or plus or one or minus depending on the outcomes of the measurements。

 and if I average over the choice of measurement and also the outcomes。That defines a channel。

 which is just a depolarizing channel， which preserves the state with some nonzero probability and replaces it with a completely mixed state with the complementary probability。

 so that defines a channel which causes the state to sync。Towards the origin of the B sphere。

 but without stinking all the way to the origin。Okay， so we have all these snapshots。

What should we do with them？Well， we stored the snapshot succinctly in a classical memory。

And as I said， averaging over the unit ensemble of unitaries and the measurement outcomes define find some channel。

If our measurements are tomographically complete， that channel will actually be an invertible matrix。

 it's not invertible by a physical map that we can do in the lab and in fact it takes the snapshot to an object which is not a physical density operator。

 but that's okay because we don't want to invert this channel in the lab。

 we just want to invert it in our classical memory by doing some classical processing and we can do that。

And then if we average over the choices of measurement。

And the outcomes and apply the inverse to the channel to each one of the snapshots。

The expectation value will be the input density operator itself。

 so if we repeat the measurement many times， we have a good unbiased estimator of the state。

But in order to be assured that we can make good predictions。

 we have to know something about the variance of our estimator。

But here's what we're going to do to make predictions。

 I have some set of operators which let's say I can describe succinctly classically。

And then for each one of those operators， I compute its expectation value and the result of the inverse of the channel applied to the snapshot。

Now。Even if I know the variance， if I don't know anything else about the distribution。

 I have to worry about our predictions being corrupted by rare， large deviations from the mean。

But there's a trick for dealing with that called median of means estimation。

 I can take our estimates。and divide them up into many bins and compute the average of the estimates in each bin。

 each one of those gives an estimate of the expectation value of the observable but where a large deviation might occur。

 but then I take the median of all the estimates and then in order for that median to deviate badly from the mean we would have to have a large deviation in half of the bins and that becomes exponentially unlikely as we increase the number of bins exponential in the number of bins。

 so once we have a sufficient size sample we can have the probability of a large deviation under control and in fact that's what enables us to guarantee that with high success probability we can predict。

A number of observables， which is exponential in the number of repetitions of the experiment。

But the shadow norm comes in when we attempt to estimate the variance of our estimator。

 so so far I've described the procedure abstractly to be more concrete。

 we should consider particular ensembles of unitaries。

So suppose we sample those unitnotaries uniformly from the Clifford group。

So then the procedure is I select。randomandom cliffiforford transformation and then I measure all the qubits and the computational basis。

 that's equivalent to simultaneously measuring a randomly selected set of commuting polyop。

And I do that many times。Now， the channel that that generates when we average over the Clford transformations and the outcomes looks like this。

 averaged over unitaries to averaged over outcomes。

 and it's an expression which is quadratic in the unitary U and quadratic。In its's ad jointint。

But the Clifford group has the delightful property of being a unitary to design。

So I can replace that average over cliffic transformations by a uniform average using a harm measure over the unitary group。

And averages over the unitary group are easy to compute because the only things that survive are unitarian invaris。

 which we can characterize and compute explicitly。So it turns out for this cliffiforford measurement scenario。

 the corresponding channel is a depolarizing channel with some probability of preserving the state。

 some probability of replacing it by the maximally mixed state。

 and that's a channel that we know how to invert。Now I want to compute the variance of our estimator。

 I can use the property that this inverse to the channel is a selfadjot operator so I can turn the M inverse acting on the snapshot into an M inverse acting on the operator。

And for the variants， I got an expression that looks like this。

Where now there a there's a square of this piece， so there are three U's and three U add joints in the expression。

 which I need to average over the Clifford group。But the Clifford group also has the delightful property of being a unitary3 design。

 so in this case as well we can replace the averaging over the Clifford group by averaging over the unitary group and get an explicit of the variance what we call the shadow norm and then we can optimize that overall or maximize it overall possible input states and that's how we estimate the shadow norm and in this case it's just a constant times the Hilbert Schmidt norm。

An example of an observable that has a constant Hilber Schmidt norm is finding the fidelity with some target pure state。

We'd be interested in the case where we can succinctly describe that target pure state。

So what I'm saying in the case of fidelity estimation。

Is that I can repeat my experiment altogether in times。

 and then I can with some small error and a high success probability。

Compute the fidelity with an exponential in N number of target states and the number of copies that I need doesn't depend on the system size at all。

Now the trouble is that although Clford transformations are nice。

 they're still a little too hard to do in current quantum platforms since they require circuits of sufficient depth。

 we need a circuit size， which is almost n squared。

We'd like to have something simpler that we really can do experimentally。

 well what could be simpler than this， we just take each one of the qubits and decide uniformly at random to measure one of the poly operatorsators X。

 Y or z。So I call that poly measurement。And in this case as well。

 it's easy to see what the channel is because。This is really equivalent to doing the single qubit Clifford group and then performing a computational basis measurement and again。

 averaging over the Clifford group is the same as averaging over the unitary group。

Now we have a tensor product of depolarizing channels acting on the N qubits that's easy to invert and then we can estimate the variance that's our shadow norm。

 use the property that the single qubit Clford group is a three design to get our estimate and what we find in this case is that we can relate the shadow norm to the operator norm of the observable that we're trying to predict。

 but there's also an exponential dependence on the weight of the observable on the number of qubits on which it acts non trivially。

But we can make good predictions efficiently if we're interested in observables。

 which have constant weight。Like if we were computing local observables， sums of local observables。

 two point correlation functions， and so on。Now， this procedure works for estimating arbitrary observables of constant weight。

 but to get some intuition concerning why the cost grows exponentially with the weight we can consider the simpler special case of just predicting。

Poly operators expectation values of poly operatorsators。

 so if we have some list of poly operatorsators that we want to be able to protect or want to be able to predict and they're all of constant weight weight no larger than W here's one of them X Z Z X acting on some subset of the qubits and acting trivialoli on the rest。

Then we do our randomized procedure and we have some non zero probability of hitting the right poly operators for in this case。

 the four operators on which。We have a non trivial action and that probability of hitting the right poly operator will go like three to the minus the weight if the weight is W。

And in this case， we don't have to bother with median a means estimation because we know how to characterize the。

Variance of the estimator directly。But it turns out then that we need to repeat the experiment in order to predict operators of weight no larger than W a number of times that scales like three to the W。

 but we can predict a number of poly operatorserators which is exponential in the number of repetitions of the experiment and that was nicely discussed by these guys before we did our work。

Now that procedure applies to arbitrary lists of poly operatorserators。

 but it's often interesting to consider poly operatorserators that have some special structure we can exploit。

 and then we might be able to do better with a deterministic procedure。

We can arrive at such a procedure just by derandomizing this randomized poly measurementa procedure。

 so let's say we have some list of poly operators。Are each acting on N qubits？

And the randomized protocol gives some guaranteed performance with high probability on our。

Concrete list of poly operatorsators we want to predict。

What we can consider is fixing one of the poly measurementsasure to be X， Y or Z。

 and then see how the procedure performs when we randomize the measurements on the rest of the operators。

 and we can choose the choice， X， Y or Z for that particular qubit in that particular poly operator to give the best performance。

And we can do that iteratively since we can compute。Bunds on the performance efficiently。

 we can efficiently step through our list of poly operatorsators one qubit at a time and each time replace the randomized polymeasurement by some fixed poly measurementasure and continue to randomize over the rest and then when we've stepped through the whole list。

 we completely do randomized the procedure。And here's an example of a case in which that helps this is inspired by an actual experiment that was done by the Innsbr group a couple of years ago with an ion trap with 20 ions they were specifically motivated by studying electrodynamics in one dimension but for our purposes we don't have to worry about that。

 this is really a spin system set of qubits where the Hamiltonian is sum of two qubit operators but without a geometric locality constraint。

 so the Hamiltonian has of order。N squared terms in it。

And then they did a very clever thing in this experiment。

 they did a variational search for states which have low energy。

But they also search for states that have a low value of the variance of the Hamiltonian。

 searching for the case in which the expectation value of the Hamiltonian squared is close to the square of the expectation value of the Hamiltonian when。

That variance is small。 It means we're close to having an eigen state of the Hamiltonian。

 So starting with some initial state and carrying out this variational procedure。

 we can find not just。The ground state， the lowest energy state。

 but other low lying energy eigenstate。 And that's what they did。

 But this is a pretty expensive procedure。 The Hamiltonian has n order n squared terms。

 The Hamiltonian squared has order N to the fourth terms。

 That's a lot of poly operatorsators that we need to predict。And in the experiment。

 they handcrafted a procedure for extracting the expectation values of poly operatorsators that they needed to find the variance of the Hamiltonian。

And actually their procedure does better for modest system size than the shadow classical shadow procedure。

 but as the system size grows in the case of the classical shadow protocol。

 we're trying to estimate a order。And for poly operatorsators。

 but the number of experiments that we need just grows logarithmically with that while their procedure actually has a dependence which is linear in system size。

 so classical shadows do considerably better for large system size。

But there's enough structure in the poly operatorsators in this case that we can get a big gain by de randomdomizing so if we de randomize the poly measurementa of the way I describe we can get a big reduction by an order of magnitude in the number of experiments that we need to do to get。

Desed error。We also looked at some applications to quantum chemistry。

 this is a case where the classical shadow。Method might be challenged because a quantum chemistry problem is a problem in electronic structure。

 it's a Hamiltonian for system of fermions and we have to encode that in qubits and when we do so some of the poly operatorsators that arise have relatively high weight。

 which means that might be disadvantage advantageous for the randomized protocol。

This is an indication of the performance of the classical shadow method。

Indicating the error in the estimation of the ground state energy for some particular benchmark。

Molecule where it can be described by a small enough number of qubits so we can do exact diagonalization so we know what the right answer is and we can test our procedure for that benchmark example the IBM group pointed out that you can actually do better because。

You can put some bias into the classical shadow protocol。

 the poly operatorsators that arise are more likely to be supported on X than on Y and z so we can set of using a uniform distribution on x Y and Z by biasing the distribution。

 we have a better chance of hitting the poly operatorsators that we're interested in。

But if we take the classical shadow protocol and we derandomize it。

 then we can do considerably better and with a smaller number of experiments。

 get to the desired error。Now I've been talking about predicting expectation values of operators。

 linear functions of the density operator。But I should emphasize that we can also estimate nonlinear functions in fact。

 if I want to compute a function which is quadratic in the density operator。

 we can just think of that as the expectation value of an observable。In the state。

 which is the tensor product of two copies of row， and we can use classical shadows to estimate that quantity by taking pairs of snapshots and replacing the first copy of row by one snapshot and the second copy by another distinct snapshot and then average over all the ways of choosing the pairs of snapshots to get our estimate。

And in that case as well， we can do an estimate of the variance of the estimator and get some performance guarantee on our predictions。

We can use that， for example， to estimate reenttroies of subsystems。And in a collaboration with the。

Ins Sp groupup， we applied that to studying entanglement dynamics after a quench in an ion trap experiment。

The cost of estimating the entropy of cost of a subystem still grows exponentially with the number of qubits in the subsystem we can't get around that。

 but the classical shadow procedure does provide a more efficient。

Way of estimating grandenttroies then previously used randomized measurement protocols。

So now I'd like to talk about。It's something we've been thinking about lately。

Which is applying machine learning to quantum problems。

And this is something that has attracted a lot of attention the last few years and there are promising results。

 but most what's been done is heuristic and we were interested whether there are situations in which we can show that machine learning used to solve a quantum problem。

 really does work efficiently and we found a couple of settings in which that's true。

 which I'll explain。The first setting is。The problem of learning properties of a quantum ground state。

So let's suppose that there's some family of。Hamiltonians。

 they're all local Hamiltonians in some'm finite dimension。

And we're guaranteed that there's an energy gap， a constant gap between the ground state and the first excited state。

For all the Hamiltonians in the family， they are smoothly parameterized by some set of real parameters。

 There may be many real parameters could live in a high dimensional parameter space。And。

What we want to do is predict properties of the ground states for various values of act。

During the training stage， we're going to suppose that we are provided with。

A sample of the ground state for some value of x that we want to sample from。

 and that's something that of course would have to be prepared on a quantum platform somehow。

And our goal is after training to predict properties of the ground state for new values effects beyond those that are encountered during training。

 so for example， we might want to learn。Aation value of some sum of local operators in the ground state at that new value of x。

And the idea that we studied。Is to convert the training states to their classical shadows and to train on the classical shadows。

And then during the prediction phase， we don't use the quantum platform at all。

 rather we're given some value of x and a description of the local Hamiltonian and then we want to use our classical learning algorithm to predict the classical shadow for a new value of x。

 and then that classical shadow can be used to predict many properties of the ground state for that new value of x。

It turns out that this learning really is efficient。 We can get by with。

Amount of training data which scales reasonably with the system size and with the dimension of the parameter space。

If we're assured that the properties that we want to predict。

Do not vary too rapidly as a function in the parameter space。

And we can actually prove that that's true。For the case of expectation values of local operators in the ground state of a finite dimensional gap local Hamiltonian。

 or in fact for any state as a function of x， which is spectrally isolated from other eigenstates throughout the parameter regime。

That guarantee that the function very slowly is obtained using the method called quasiiadiabatic continuation or spectral flow。

But once we know it's true， then we're assured that this prediction procedure is really efficient。

 all the learning is classical。We learn using the classical shadows as inputs and we predict classical shadows for the new values of x。

 but we still need the quantum platform to somehow prepare the ground state for the values of x encountered during training。

And to extract the classical shadow by measuring the ground state。

So we've done some numerical experiments to see how well this works， here's one example。

 it's an example chosen because it corresponds to a system studying in a real experiment。

It's an array of Ridberg atoms altogether 51 atoms held in a tweezer array in one dimension。

 you don't have to worry about that so much you can just think about it as a system。With 51 qubits。

With a Hamiltonian that。呃。Aside from the overall scale is parameterized by two real parameters。

And as we vary these parameters as we increase one of those that favors that the qubits take the value1 overtaking the value zero。

 but as we to increase the other parameter that disfavors to ones sitting at neighboring sites in the chain or even nearby sites in the chain。

 so there's a competition between those two effects。

 which gives rise to an interesting phase structure as I've indicated here。所我。

What we do is we select some points in this parameter space that's our training data。

 those are the points that are shown by circles which have the dark。Boundary around them。

 they're altogether 20 such points selected here。 And then after training。

 we want to predict properties at。New values of the parameters。

 and those are the ones indicated by the cross， the diamond and the star。Now in this case。

 it's 51 qubits， but it's a one dimensional chain so you can use DMRG to compute accurately the exact properties of the system and estimate in particular using DMRG the expectation values of local。

Observable， so we know what the right answers are and we want to test how well our training procedure performs。

So。We can use the classical shadow after training to predict a variety of different local operators。

 but just to get an idea of how it works， let's say we want to predict site by site the expectation value of the poly operator Z。

For the point indicated by the diamond。You can look here and the solid curve is the。

A right answer that we get from the DMRG calculation。

And the diamonds are the predictions that come out of our prediction model。

 and you can see they match up with the DMRG results pretty well。If we did something more naive。

 if we tried to predict at the diamond point just using the closest buy point in the training space。

 then we wouldn't do very well at all， that's shown in the next plot， it's the same DMRG data。

 but here is the data from the neighboring point which doesn't match up with the red answer very well。

And here similarly we can look at the point indicated by a cross this is actually in the phase of the system where ones and zeros want to alternate in the ground state 101010 and so when we look at the expectation value of Z we see these oscillations again the solid curve is the result from DMRG and the crosses are the result from the prediction model and if we just use this near by point to try to predict we don't do very well at all so the prediction model really is leveraging the results。

From the training sample beyond just the points which you're closest by。

Now the truth is in this case， our rigorous theory does not directly apply。

 it doesn't guarantee that we'll get good predictions。

 and the reason is that there are phase transitions in this parameter space， the theory applies。

 if we have a constant spectral gap throughout the parameter region that we're sampling from and that's not the case here because there are really three phases but we find nevertheless that the predictions work pretty well even though some of the training data is coming from other phases。

 that wasn't guaranteed to work， but it works pretty well。

The other thing I'd like to discuss is using machine learning to identify quantum phases of matter。

So the idea here is that during training， we are offered samples of quantum states， which。

A representatives of either either one of two possible phases， let's say A and B。

And those samples that we have during training are labeled。

 so we know which ones come from phase A and which ones come from phase B。And then after training。

 our goal is when we encounter a new quantum state that doesn't carry a label。

 we are supposed to predict that phase label with good accuracy。Again， the idea is。

To take the quantum states that we encounter during training， convert them efficiently in our。

Eximent platform into a classical shadow and then to learn to classify the shadows and then during prediction when we have a new quantum state。

 we convert it to its classical shadow and then we try to assign the right label label to the shadow。

The procedure we apply to learn here is kind of a standard scenario in learning theory。

We take the input data during training。嗯。And prediction。

And we map that to a high dimensional feature space。

 but the input data here is not the quantum state itself， but it classical shadow。

And then in this higher dimensional feature space， we try to find a linear classifying function。

 a hyperplane in the feature space that separates the data from the two phases with。

Phase A points on one side of the hyperplane and phase B points on the other side。And if the。嗯。

Points from either phase don't come too close to the hyperplane。

Then it's relatively easy to learn on that linear function that classifies into phases。

Now to show whether this will really work， we need an assumption。Which is physically motivated。

And that is that there is some classifying function that can be used to identify phases。

Which is a polynomial in few body marginal density operators。

We don't have to know that function in advance， we're going to learn it。

 but to guarantee that this procedural work， we need to know that it exists。

The type of thing I might be interested in is distinguishing a trivial phase from a topological phase。

And it's often said that in order to identify a topological phase， I need some kind of。Non nonlinear。

Or sorry， some non local order parameter to identify it。What really happens though， is。

As long as the correlation length is finite。In the topological or trivial phase。

Then we can look at a volume， which maybe is a little bit larger than the correlation volume。

 and that already suffices to distinguish the two phases。

An example of that would be in the case of a topological phase。

 we can compute something called the topological entanglement entropy。

 which is somewhat different scaling than entropy in the trivial phase。

 so we can tell the difference and that scaling already kicks in when we consider subsystems with the size larger than the correlation length。

So we have to assume that such a classifying function exists， but if it is。

 we can build our feature map so that it's guaranteed the learning will be efficient。

 meaning the amount of training data and the classical processing that are required are polynomial in the system size。

As we get closer to a phase boundary， what we expect to happen is that we have to look at larger and larger subsystems in order to distinguish the phases and then the learning gets more and more difficult。

 but for a fixed correlation length， we can efficiently learn to distinguish the trivial and topological phases。

 for example。So again， we did some numerical experiments。In particular。

 the case of trying to distinguish the trivial phase from the toic code。Topologically ordered phase。

Now。What it's。One way of defining what you mean by top logical order。

Is that it's not possible starting with a trivial state， a product state。

To create a state in the topologically ordered phase with a local circuit that has constant depth。

Now here of course we're considering some finite system size。

 so exactly what you mean by constant depth， this a little murky in the numerical experiments。

 we considered the Tory code on a 10 by 10 lattice， so the code distance is 10， there are 200 qubits。

And we can take the。Exactly solved a cattaath model as a representative of the topologically non trivial phase。

 and then we can consider applying some low depth circuit。

To that state to get some other representative of the topological phase， and likewise。

 we can start with a representative of the trivial phase。

 a product state and apply some local low depth circuit to that and then what we expect is that if the circuits of sufficiently low depth。

 we will be able to classify the states to tell the difference between the topological and trivial states。

So what's shown。Over here on the left。Is that we take the feature space？嗯。

To which our classical shadows are map。And we project。

The geometry of that feature space down to a few dimensions， two dimensions in this case。

And you can see。🤧That the representatives of the topological phase are well separated from those in the trivial phase。

 so it's not that difficult to learn a linear function to find a hyperplane that separates them effectively。

What's shown over here on the right。Is as we increase the circuit size。

 how the distinguishability between the two phases is compromised。

This is actually just projecting down to a one dimension。

 but with the data arranged in a way that gives you a visualization of how the data is distributed in that one dimension。

So remember， I'm talking about the case where the code distance is 10。

The case where I have the zero depth circuit applied that just means I have Kaya's to code and product state。

 and those are easy to tell apart when we take their class shadows。

 but then as we apply circuits of increasing depth to both the top logical state and the trivial state。

 the ability to distinguish gets worse and worse and when the data here is actually shown for the case where the circuit that's applied has depth three。

 we can still separate the two pretty well， but by the time we get up to a depth which is about half of the code distance。

 then our ability to predict is being badly compromised。Okay， so our main results from。

Studying applications of machine learning， quantum problems are summarized here。

One theorem concerns learning the properties of ground states。A statement is。

That for any smooth family of Hamiltonians。In a finite spatial dimension。

 there are local Hamiltonians， I should have said。嗯。Where there's a constant spectral gap。

 there's a classical machine learning algorithm which can learn to predict an efficient classical representation of the ground state。

That can be used to approximate few body reduced density operators up to a connere。

 and the amount of training data and the computation that we need is polynomial in the dimension of the parameter space and linear in the system size。

The procedure is that during training， we take the input states。

 we translate them into classical shadows and we actually train on the classical shadows and in the prediction phase。

 we don't use the quantum platform at all， rather we predict for a new value of x what the classical shadow is。

 and then we can use that to predict properties。And the second result concerns identifying quantum phases matter。

And it says that if there exists a polynomial function of few body reduced density operators that does classify phases。

Then there's a classical machine learning algorithm that can learn that and can predict phases accurately。

 and the required amount of training data and the computation time are polynomial。

In the system size and again， the procedure is to take an input state during training or prediction and to translate it into a classical shadow and we learn to classify the classical shadows during training and then we can predict the correct lab label when we get new input classical shadows in the prediction phase。

Hi， John， there's a question on the Q&A about this， so Frederic Ca。

 is there some direct connection to those ground states of being an area law and being in principle representedable by a Tensor network？

嗯。No， so actually， so here's an important point。嗯。We can learn properties of ground states。

By using the training data， which would be hard to learn if we didn't have the training data。

 so if we only had the description of the Hamiltonian and we tried to construct an approximation to the ground state and use that to predict properties。

 that might be a very hard problem。But what we're learning is that if we have a quantum platform which provides us with samples of the quantum state。

 then by measuring those and by doing measurements that are not so difficult for a real quantum platform。

Then we can proceed to make predictions about the properties of Hamiltonians in this paramettriized family。

 even though we couldn't do that directly without making use of the quantum platform。In fact。

 we did the following thing just。To illustrate the point。You can encode in a quantum state。嗯。

A solution to a factoring problem。And you can choose that to be a ground state of some suitable local Hamiltonian。

And furthermore， because we can use shore's algorithm that state could be easy to prepare in a。

Quantum platform。And now we now are given samples of that easy to prepare quantum state。

 easy to prepare on a quantum platform。And by measuring them and then training on the classical shadows。

We can。Actually solve the factoring problem。But we were able to do that because it was encoded in the quantum state itself。

So that's an illustration of how by training on this classical data。

 we can do things that we couldn't do if we didn't have access to the quantum platform at all。

I think I was done with this slide right Okay， actually I'm done with the talk， so here's a summary。

So I've told you about classical shadows of quantum stakes。

This is a procedure which is actually feasible in the lab。

For translating a state from quantum language into succinct classical language。

And that classical data can be easily stored and by doing efficient processing。

If we consider some list of properties， though。Have satisfied suitable criterion。

Then we can predict accurately with a high probability of success and properties with just measurements of ordered logm copies of the quantum state I didn't actually talk about this。

 but we can show that the number of copies is actually asymptically optimal if we're limited to measuring the states one at a time we can do better if we can make contangling measurements across multiple copies。

 but that would be much harder to do with the quantum platform。

The sample complexity and the classical processing time。

For making predictions can improve on methods that have been used previously。

And with classical machine learning， combined with classical shadows。

 we can effectively address some quantum any body problem。

How this talk has been about making predictions and I'll predict that classical shadows will be used fruitfully。



![](img/223d60d05c8adf8f51c975bf2897242b_1.png)

In the years ahead to develop further applications。Of near term quantum platforms。Oh。

 thanks a lot for listening。Great， thank you， that was a fantastic talk。😊。

Let's see if there are any more questions， so Adam or Ra do you Yeah， I see soon Juan has a question。

You can go ahead and ask it directly。Thank you for nice talk。嗯。Sorry， can you hear me？Yeah。

 I have a question about the learning the proper of the ground state。So unlike the shadow tomography。

 in order to predict the property you need to somehow interpolate or extrapolate within the parameter space of the Hamiltonian neuro cases is x。

 so could you explain how you smoothly interpolate those data from the shadow tomography method？



![](img/223d60d05c8adf8f51c975bf2897242b_3.png)

How we smoothly interpolate the data？嗯。Well， the as I said。We need the feature。

That the properties that we're going to predict with the classical shadow actually have some bounded gradient。

As a function of the parameters which label the family of Hamiltonians。

So really what we do is4ier analysis。Knowing that。Bound on the gradient。We can reconstruct the。

You know， a smooth version of the classical shadow。

In which we throw away very high wave number Fourier components。

 so the number of Fourier components that we actually need to learn is a reasonable number and that's why without a lot of training data we're able to learn good enough approximation to the classical shadow that we can make predictions。

Thank you。😊，Yeah， I see May next A Hoot， you want to ask your question。Yeah。

 so this might be a bit outside your ethereem， but what do you feel about that？嗯。😊。

If your for the machine learning learning phases， if your wave function was not generated by the deterministic Hamiltontonian but by some stochastic process。

 so you had one shot， one shadow for each wave function。

 but you could still classify the states that you get whether they're in the topological or say。

Trivial， theyre topological or trivial， would you still be able to use this method， do you think？

I'm not quite sure what you mean because there's no。There's not really a Hamiltonian。

In the training tasks， there's just a bunch of states。And。You know。

 we're trying to classify the states。So。Well yeah， but what you need to give instead of a Hamiltonian is there is a stochastic process that is parameterized by some parameters。

 x。And we know that for certain values of these parameters， so what is popular now， for example。

 is a quantum circuit with measurements， for example。

So depending on what probability for certain types of measurements。

 you either have a steady state that's topological or non topological， for example。

 but then you just have a single shot for each state you produce， so you have an ensemble。诶。哎。

I think you can still parameterize it。I think the question makes sense I don't know if it actually falls into your theorem I guess to decide whether it does we have to see。

Whether that would invalidate the assumption underlying the theorem。

Which is that a polynomial function of a few body density operators suffices to classify。That's fine。

 that's the same thing because you have the states you get are topological and if I look at a reduced density matrix of say four or six sites and it's more than a two side correlation length。

 then I can probably tell topological from nontopological。

 but I have just a single access shot that's the problem。Well， I don't know， I mean。

 you're going to give me samples of these quantum states。

And if indeed there's a classifying function， which is polynomial。

 I'll be able to learn it if it's you know polynomial and constant size of reduced density operators。

 even if you can only sample one from each state， ones from each state。

One I don't know what you mean by one from each state。

 I'm going to I'm going to measure all the qubits each time。Right。

 think that's how I make the shadow， but the next time you get this state。

 it'll be a different state。You cannot repeat on the same state like you can oh okay yeah so no we can that still works if you have we can say so that's the only issue oh well actually wait a minute i'm not I'm not totally sure I'm sorry you know it's a good question in fact I didn't say this。

But what we actually proved。Is that for each sample you have to repeat the measurement you know some sufficient number of times yeah I'm pretty sure thats okay right so it's a good question I should have said this so you have to sample enough points。

 but for each sample you have to in order to get from the classical shadow a sufficiently good representation you have to predict a sufficient number of times and in both cases the number of times you have to repeat for each copy and the total number of samples that you need those are polynomial and system size。

But died。You know， it couldn't you。You have to have enough repetitions of measurements of the same state。

 yeah。But related question， is it a fundamental because as you said。

 if youre swim somephoier space and a smoothness， why do you need to sample multiple times for a single point Okay。

 well we're talking about two different things now I think。

Yod was asking about the second theorem you're asking about the first。

So in the case where we're trying to learn this you。

 truncated bandwidth limited version of the classical shadow to predict properties。

 it is enough to measure once for each sample。But our proof that you can classify phases。嗯。

Works only if you measure each of the copies during training a sufficient number of times。嗯。😊。

My question is actually related to Ehoots if I may go next， thanks Adam， John。

 you were very or fairly positive in the end about the potential use of quantum machines for platforms we're generating the states needed for classical shadow tomography as you described。

 but these are noisy machines in practice， and I'm curious how robust your two theorems are in the presence of finite amount of noise and it would not just be the stochastic sampling or one shot that Ehood ask but the kind of realistic noises that we see as you call the NC error machines。

I have a second follow up question on that afterwards。Well， indeed。

 this is an important point and I didn't mention it in the talk for lack of time。

But there have been a couple of papers addressing this。

 including one by Steve Laie and collaborators， I guess Steve is here。

And so what will happen if there's noise in general。

 is that our estimator will no longer be an unbiased estimator。

And so we have to in our inversion of the channel， include some inversion of the effect of the noise。

And what？Other authors， not us。Have addresses that under assumptions about the noise being sufficiently nice。

 like independent noise， for example， we can characterize the noise well enough to do that inversion and get pretty good robustness of the predictions。

The follow up， which naturally arises from what you just described is that your procedure。

Should also work for classical shadows of classical systems， classical stochastic systems。

 in principle， because the density matrix of those can just be a statistical distribution。

But there it's known to be fairly difficult because of the difficulty of noise noise is typically not biased。

 noise is typically not well behaved do you actually think that they will work in practice？Well。

 I don't know， I guess it depends on the noise。A。We have not in our。Work on classifying phases。H。

Made any claim about No's robustness at this point。And。I don't know。

 I would just have I don't have a good answer I can make。An optimistic guess。

But you can take it or leave it， I think if the noise is。You know。Not highly correlated。And。That。

It might not be that different。From what I described。

 which is we just applied some random local circuit。

To the state and we can still recognize that it's in one phase or the other。

And so maybe it would be fairly robust but。That's beyond the scope of what we've done so far。

Right thanks John Mohamd， would you like to go ahead and ask your question it's actually related to the previous question but more specific and it's very naive in the second part of your talk you showed that the first principal component can tell whether we are in topological phase or not。

How can we make sure that actually that component corresponds to the biological order in present or absent and not just the artifact of the Christtine Hamiltonian that we have implemented？

Well， in the context of the theorem。You know， that followed from the assumption。

You know that this polynomial function exists that classifies phases successfully， in other words。

That you know it takes a value which is greater than one in one phase and less than minus one in the other phase。

And then our feature map is designed so that if such a function exists。We can learn it。

So maybe what you're questioning is。Whether to believe the assumption。

Or the assumption or this principal component that I have now identified corresponds to like entangleular entropy。

Yeah， well， the point of the principal component analysis was just to illustrate the idea。

 we don't make use of principal component analysis in the proof。m，You know， we just u。

Make use of the existence of a classifying function with certain properties and we design the feature map so that if it exists。

 we can learn it。And I showed the principal component analysis just as a nice way of illustrating。

 you what happens or the distinguishability of the phases。

As we try to mockck them up more and more by applying local random circuits。Thanks。olPeter Love。

 would you like to unmute。Hi John， thanks for a nice talk。

You gave a nice example of one of the cases where you needed。

Measurement data by constructing this factoring example。

 do you have any examples where you don't need the quantum device？

So where you can do things with classical shadows completely classically。Hm。I'm not sure what the。嗯。

Formulation of the question is exactly。Yeah， so。Do you know of a subset of states？

Where you can obtain the classical shadows efficiently， classically， I guess。嗯。

I still don't understand Peter， so is it a question about？Whether。

Whether we can go beyond beyond the guarantee that I described for。

Some states that we can describe classically， I mean， if we can describe them classically。

 then I guess we don't need the classical shadow necessarily。

In order to predict things from happening。Maybe we can take that further offline。

 we should move on to the panel， but before that， thanks John for a fantastic presentation。Okay， so。

So。Let me introduce the panelists as Omit pins up the videos of the panelists。

