# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p19 -19-Ph CS 219A Lecture 17 Quantum Simulation.zh_en -BV1KgffBoEUc_p19-

![](img/ee0a992e0912b6e1c494ca7b10173dd9_0.png)

Okay， so here we go。Welcome back to Comp Science Phic 219 A， I usually say it the other way around。

 but it is after all， both a computer science and a physics class。

It hard to believe we're closing in on the end of the term。It's just rocketed by。

This will be the second to last lecture in the original syllabus， I said there would be 20 lectures。

Then I realized we were running a little ahead of schedule。And in the end， there will be 18， I am。

Cutting one of the topics， which was in the original syllabus。

The lecture on the general solution to the obbelian hidden Subgroup problem。

There are notes about that in the revised chapter six notes。If you're interested。

 but I wanted to move ahead more quickly to discuss Groover's algorithm。

 as we did in the previous lecture， so you'd be prepared for homework problems relating to that。

And in this lecture and the next one， we'll cover our last two topics。Today。

 using quantum computers to simulate quantum systems。And in the next lecture。

The QmaA completeness of the problem of estimating the energy of a quantum system。So let's get going。

So Feynman actually already foresaw。40 years ago when he first。

Proposed the idea that a quantum computer would be able to vastly outperform。

Classical computers for some task he had in mind the task of simulating how quantum systems behave。

 that's a problem which is certainly of great interest to physicists in many areas of physics and also to chemists and it does have。

Applications as well to well everything having to do with materials and chemistry。

 including human health， pharmaceuticals， agriculture。Energy production。

Improving the sustainability of our planet。And all those things。

 which are certainly important and where we do expect quantum computers will eventually make a contribution。

And in this example， I want to talk about。Two ways in which we can use quantum computers to solve quantum problems。

In both cases， we'll consider a quantum system with a so called local Hamiltonian。

 and I'll explain what that means。In the lecture， but I guess I'll tell you now that just means the Hamiltonian can be written as a sum of terms and that each of the term x non trivial。

 each of those terms acts non trivially on just some constant number of qubits independent of the system size。

And we care about local Hamiltonians， especially not just because quantum computers can deal with them well。

 but because we think that the phenomena we observe in nature。

Can be described as resulting from the dynamics of such a local Hamiltonian。And for such systems。

 for local Hamiltonians。We'll see that with a quantum computer time evolution。

Of the system with a specified volume for a specified time with an error which is polynomially small as the volume gets large。

That can be simulated with。A quantum circuit of polynomial size。

 polynomial in the spatial volume and in the evolution time。And the second task we'll consider。

 which turns out。To be related。Is。Estimating the energy eigenvalues of a local Hamiltonian。

Measuring the energy of a quantum system to in accuracycur which goes like one over polynomial in the volume of the system under consideration。

That too， can be achieved。Using a quantum circuit which has polynomial size。

 now polynomial in the volume of the system。Assuming we're able to prepare somehow a quantum state in our quantum computer。

 which has a non negligible overlap going like one over polynomial of the volume with the energy eigenstate in question。

That's an important caveat， as we'll see in the next lecture。

So let's start with considering evolution， well first let me just say again what I mean by a local Hamiltonian。

The Hamiltonian can be written as a sum of terms。Each one of the terms x on a number of qubits at most k。

And K is a constant， doesn't depend on the size of the system。

And each one of the terms in the Hamiltonian has a bounded supernorm。

All the terms are bounded in norm by some constant， which I'm calling the Lch。

What do we want to do with this local Hamiltonian， we want to solve for the dynamics that it generates。

There's a time dependent Schchrodinger equation， which describes how state vectors evolve governed by this Hamiltonian。

That the state at time T。Is related to the state at some initial time zero by a time evolution unitary operator。

 U of T， and U of T satisfies this first order differential equation， the Schrodinger equation。

The time derivative of U with respect to T is given by minus h of T where H is the Hamiltonian at time T。

Acting on U of T。And to solve this first order differential equation， we need a boundary condition。

 which is that at time zero， the unitary is zero， so the evolution begins。At time zero。

 and it's determined。For subsequent times， the evolution is determined by this Schchrodinger equation。

Often in physics， we consider Hamiltonians which are time independent。

 but we're going to allow the Hamiltonian to depend on time。

 there will be some kind of technical condition that the Hamiltonian not vary with time to rapidly。

 but we dot allow to allow it to depend on time for the purpose of our discussion。

So there is some ideal。Quantum state， there's some specified initial state and in practice I'm going to want that to be something I can load into a quantum computer efficiently。

And some ideal state determined by the Schchroding equation at the later time T。

And what we want to do is。Create a state in our quantum computer。Which is close to that ideal state。

 our criterion for close will be that。The norm of the difference between the actual state that we construct with a quantum circuit。

silda。And the ideal state is less than delta， well here I said Delta equals a constant。

 but actually I'll sometimes consider deelta getting small with system size。But anyway。

 there's some error delta， which we can take to be the deviation in the norm。

You know I could have talked about some states are really raised。

 I could have talked about distance between density operators。

 but it'll be fine to consider state vectors for our purposes we want to approximate the actual state。

Determined by the evolution， determined by H of T。At some later time。Now。

 normally when we want to compare。What a quantum computer does to a classical computer。

 of course we want to compare with the classical task， I didn't describe this。As a classical task。

 I said the task was to prepare a。Quantum state and I don't necessarily want to claim that that quantum state has a succinct classical description and at any rate that's not what the quantum algorithm does。

 It doesn't give me a succinct classical or any classical description of the state。

 it just gives me the state。 so if I want to compare to something that a quantum computer can。

You know， compete with a classical computer if I want to consider a task that a classical computer can perform and then ask whether the quantum computer can speed that up。

 then we can imagine we make a measurement at the end。

That there's some observable that we're interested in at time T， we measure the observable。

And by doing so， we are sampling from the probability distribution of outcomes。

For that measure observable in the final state psi of t， that's what we want。

The computation to do and for。Classical computers we think it's a hard task in the sense that。

We don't know how to do it。Without using resources that are exponential in the size of the quantum system。

 of course。As we've discussed before， the state is just a vector in a Hilbert space。

 the unitary operator is just a big matrix， but for Nqubits it's a huge matrix。

 it's of exponential size it's 2 to the n by 2 to the n and to actually classically represent u of T。

Is hard to do of course I don't necessarily have to classically represent u of T in order to solve the problem of sampling from this distribution。

 but we just don't know a way of doing it any way of doing it。

That doesn't require exponential resources， and it's not for lack of trying。

His assistant chemists have been trying to come up。

With better classical algorithms for simulating the evolution of quantum systems for many decades。

 but still。After all that effort， the best algorithms that we have。

Have a runtime which is exponential in the number of qubits on a classical computer。

 and we want to see whether with a quantum computer， we can do better。Now。

For a general K local Hamiltonian， the way I've defined it。

 there isn't any geometric constraint on how the qubits coupled one another。

So I could have a term in the Hamiltonian。Which acts non trivially collectively on any set of Kqubits。

And I can collect together in the Hamiltonian all of the terms。That act on a given set。

Of Kqubits and then the number of such terms that I would need。Would just be at worst and choose K。

That would be the number if every set of K qubits had some term in the Hamiltonian acting on it。

But what we're often interested in instead are geometrically local Hamiltonians and what that means is that only neighboring qubits are coupled to one another when the qubits are arranged in a lattice in some number of spatial dimensions。

 let's say in D dimensions。And so what we mean by geometrically local is we imagine the qubits arranged in a D dimensionsional lattice for some fine ID。

 and all of the terms in the Hamiltonian that act collectively and nontrivily on some set of up to K qubits。

Act inside a constant size volume independent of the system size so in other words。

 there aren't any very long range interactions among qubits the size of the ball that contains an interaction term。

Is the range of the interaction geometrically local means that's a constant。

And then the number of terms in the Hamiltonian that we need really just scales with the volume of the system。

 no matter what the number of dimensions is， if we consider this ball of constant size， you know。

 relative to the spacing between points on the lattice that's。

Going to contain some constant number of qubits， but furthermore。

 each qubit will only be contained in some constant number of balls。

So such terms will just scale with the total number of qubits。

And the geometrically local case is what we think fundamentally。Is the right way to describe nature。

 so that case is of special interest。And as far as we know。

 the number of spatial dimensions is three。In the world。

 although there's some controversy about that。But at any rate， it's although well。

 whether physics is really geometrically local， once we start worrying about the effects of gravitation is a subtle question and maybe the answer is no。

But for the purposes of the physics， we understand best。

 like the particle physics that we've studied in high energy physics experiments。

Local Hamiltonians seem to be a quite adequatete description。

 so that's mostly what I want to consider here。And so we want to evolve for some time T。

But we're going to do that with。Quantum gates with some circuit of operations acting on the qubit。

So I'm going to approximate the continuous Schrodinger time evolution by a sequence of discrete steps。

 That's the way we always simulate time evolution on a。On a computer， because we can only。Well。

 the analog devices I guess are different， but with digital computers we always approximate time evolution as a finite number of discrete steps and likewise if we're interested in continuous system spatially to put it on a computer we always consider as I described a minute ago。

 some kind of lattice which approximates that continuum system。

So we're going to consider processes typically that。you know。

 take place on some distant scale of physical interest。

 so we'll want the lattice spacing for our model system to be small compared to that physical scale of interest。

 so that although it's really fundamentally discrete the quantum system can capture approximately to a good approximation。

 the behavior of a continuous system。Okay， so we're going to divide the time evolution into little time steps of with delta。

 so the total number of such steps if we're going to evolve for time t will be t over delta。And now。

 the big problem that we have。Is that the Hamiltonian conveniently is written as this sum of terms which have bounded support。

 which act on a constant number of qubits， but those terms don't commute with one another。

So that makes solving the Schchroding equation challenging。

What we're going to do is something very simple， and then this can be systematically improved to get even better approximations。

We're going to consider a time step that's sufficiently small that if I want to evolve。

For time Delta。Well， first of all， I can ignore the time dependence of the Hamiltonian during that time interval。

 we can take it as effectively constant for a constant Hamiltonian。

 the solution to the Schchroding equation formally is just the evolution operator is e to the minus I h times the time interval in this case delta。

 so ignoring the time dependence of the Hamiltonian over that。

Time interval where we're just interested in constructing this operator。And。

That is the exponential of a sum of non commuting terms， kind of hard to deal with。

But we're going to just， if they were commuting， we could just write that exponential of a sum as a product of exponentials。

Now we can't justify that exactly when the terms fail to commute with one another。But we can。

Except that as a first approximation to the operator we're really interested in。

 and that's what I'm going to do。 I'm going to approximate the exponential of the sum。

By a product of exponentials， and that's going to introduce Sam error。

Which we're going to have to introduce or which we're going to have to analyze。

 we're going to have to estimate that error。So let's do it。So what I would like to know。Is I have a。

Exponential of a sum of operators and now just to simplify the notation。

 I'm calling the operators that I'm summing over。A sub a where a is an index that keeps track of the operators in the sum。

I want to know how well is that approximated by the product of the exponentials？ok。

And all I'm going to do is I'm going to treat a as a small quantity。

 what I have in mind is that it has a small operator norm。

And I'm going to try to estimate actually the operator norm of the difference between these expressions。

 the exponential of the sum and the product of the exponentials。

 and I'm going to do so making use of the power series expansion of the exponential。

 and I'm going to do the sum up to a certain order I'm going to ignore the higher order terms。

 and I'm not going to go into the detail here， but you can estimate those higher order terms in the power series expansion of the exponential to make sure that we have a good approximation when we neglect the higher order terms。

So let's just do it。So we have the exponential of the sum here。And。嗯。We expanded out。

 so the power series expansion of an exponential。One plus the1 plus the sum。

And then plus one half the product of two such sums。

 so I can write that as now I'm summing over two indices A and B。And。One of the。Operators。

In the exponential is on the left and I label that with the index A and the other one is on the right。

 I label that with the index B for a not equal to B， these guys may not commute。

 but I'm summing a and B over the full index set， so that's just the same thing as the square of the sum over a of a sub a。

And now I want to subtract away this product。And。For each exponential， the exponential of a sub A。

 I expand that in a power series same way。So one plus the linear term a sub a， quadratic term。

1 half a sub a squared， and if we wanted to， we could keep track of higher order terms two to estimate the error that we're making。

Okay， so now。I want to expand this product over a， so this is just the same expression I had before for the exponential of the sum。

Here。And now I want to expand the product of these power series。Up to quadratic order in A。

And there are two ways in which I can get terms which are of quadratic order。Well。First of all。

 the only way to get one is if I take one from every one of the products indexed by a。

And then the only way I can get linear terms is if I take one everywhere except for an A in one of the factors of the product。

 and then all of the possible factors in the product contribute。

 so that's just one plus the sum over the index a sub a。

But now there are two ways to get quadratic terms， one is that I take the quadratic term from one of the factors in the product and one everywhere else and that gives the sum over a1 half AAA squared。

 and the second way is that I take the linear term in one of the factors and the linear term and another factor and then one everywhere else。

And in that case， I can write it as the sum over。A less than B。Of。A sub A。A sub B。Hold on a second。

Okay， sorry about that， I'm back。So the reason it's a less than B is that the factors in the product are in a ascending order。

 so the first。Factor is。A sub1， the second one is a sub2， the third one is a sub 3 and so on。

 So the a with the lower index is always to the left of the a with the higher index。

 So only the ordering A sub A， A sub B where the index A is less than B occurs when we expand this product。

All right。So now。First of all， we notice the ones cancel in the difference。

 and so to the linear terms， those are the same in both expressions。

The quadratic terms are going to be the first non trivial terms。Of course。

 they wouldn't be there at all if everything commuted。

 so the quadratic term is going to have to arise from the failure of the different A's to commute with one another。

So let's write this sum over all A and B of AA times Ab as two separate sums。

There's the terms with a less than B。AAAB and the terms with A less than B A B AA。

 so that keeps track of the two possible orders。And it's the same thing as summing over a not equal to B we're not including the a equal Sp case because that got canceled between this sum where we have one half Aa squared and this sum from expanding the product so it's only the terms with a not equal to B that survive when we take the difference and then here I've just subtracted a way this term。

In the expansion of the product。There it is。Minus sum over a less than b of AA AB。Okay。

 so you see for the terms with a less than B AA A B， I have a one half here and minus here。

 so that becomes minus1 half。The terms with A less than B of AA AB。

 but then I also have one half the terms with A less than B， A B AA。

 so altogether that's going to give me minus1 half the sum for a less than B。AA A B minus A B AA。

In other words， the commutator of AA with AB。So of course that would be zero if the terms were all commuting。

And then the higher orders are cubic order in A and so on。So now remember。

 the case we are interested in is when the terms are the terms in the Hamiltonian。嗯。

And the time evolution operator is e to the minus Ih delta。

So the exponential of the Hamiltonian times minus I delta is going to have the sum over a H sub A。

 and then here I have the product。Of E to the minus Iha delta。

 and so because I have the I' and that gets squared that cancels the minus1 half here。

 and there's a factor of delta squared in the quadratic term。

 and then I have the sum over all a less than B of the commutator of H with HB and then the higher order terms which are a order delta cubed H cubed。

So if I'm interested in the。The norm， let's say， the soup norm of the difference。

Between the actual time evolution operator。Governed by the Hamiltontonian for time Delta and our approximation。

 which is a product of these。Single terms in the Hamiltonian E to the minus Ihi deelta。

What's it going to be， well， there can be a contribution from any pair of terms in the Hamiltonian that failed to commute with one another。

Let's suppose we're talking about the geometrically local case。Well。

 then what does it mean for two terms to not commute with one another， then they have to。

Have qubits in common among the sets of qubits on which they act。

Okay in the geometrically local case， then for each term in the Hamiltonian there's just some constant number of other terms that fail to commute with it those are the ones that are nearby contained inside some constant sized ball。

 so the number of commutator terms that are non vanishing。

In which each term in the Hamiltonian participates is a constant number。And so。

I can take the delta squared out and then remember we're taking the norm。

 the soup norm of each term in the Hamiltonian to be bounded by H。

 so that means that we can bound the commutator by something of order little h squared and then M here。

It's just the number of terms in the Hamiltonian。Each term in the Hamiltonian has only a constant number of other terms it fails to commute with。

 so the number of nonvanishing commutators is proportional to the total number of terms in the Hamiltonian in the geometrically local case it can scale differently with the number of terms in the Hamiltonian when we allow long range geometrically non-local interactions and we could do that too。

 but to keep the discussion simple， let's just consider the geometrically local case here。Okay。

 so now we want to carry out。T over delta such steps here I've described our approximation to the evolution for time Dlta。

 we really want to evolve for time T， so there will be T over delta steps using our approximation the error that we make in each step we can bound by the number of terms in the Hamiltonian M。

Delta squared our time step size，8 squared are bound on the Hamiltonian of each term。

 so the total error， which I'm calling deelta goes like this。

And so I can use that to estimate how small I need the time step capital delta to be in order for the total error for time T to be less than little delta。

 so I do that just by dividing here by MTt h squared and the conclusion is that we want the time step capital delta to be of order the total error little delta divided by h squared MTt。

Now。Each one of the steps that we carry out。Involving a local term in the Hamiltonian。

 each one of these e to the minus H deltas。That we can achieve with。

A quantum computation that just acts on some constant number of qubits and we have some universal gate set and so we're going to approximate that by some sulie kya polylo factor。

 but let's ignore that。For now， and just count the number of these local steps that we have to put together to simulate the evolution of the full system for time T。

 that is the number of operations of the form e to the minus Iha delta。And so how many is that， well。

 it's the number of terms in the Hamiltonian， which I called capital M times the number of steps。

 which is t over delta。So the circuit size that we need is going to be capital mt over delta times a constant。

 Now let's put back in what one over delta is it's8 squared mt over little delta。

 one over capital delta where delta is the time step。

Is going to be order8 squared mt over little delta， the total error。

 so I can write this as8 squared mt squared over little delta。

That's the number of gates I'm going to need where I think of a gate as one of these operations of the form e to the minus Iha delta。

Which is acting on no more than K qubits。ok。And in the geometrically local case， as we already noted。

 the total number of terms in the Hamiltonian。Scales with the number of qubits because each qubit participates in only some constant number of terms because of the geometric locality。

So up to a constant， I can also write this as the so called circuit size。

 meaning the number of these elementary steps。嗯。That we need to simulate the evolution with a total error error little delta is8 squared number of qubits n times time evolution time T and T the quantity squared divided by little delta。

 the total error。So。Little end times t， you can think of that as the volume of space time that we're simulating because the volume by which you can think of as the number of lattice sites that we're including in our simulation is going to scale with the number of qubits。

So the physical volume is going to be the number of qubits times the volume per lattice site。

 but that's just some constant， so the Nt squared is essentially the spatial volume that we're simulating would no matter what the number of spatial dimensions times the time so I'm calling that the simulated space time volume。

And so if we fix the error delta。嗯。Then。That means since H is also some constant。

As we increase the space time volume， the circuit size。Grows like the spacetime volume squared。Now。

 if you really want to use some universal gate set。

 like some set of twoqubbit gates or something to build our circuit。

 then we're going to have to approximate each one of the e to the minus Iha delta factors to an error which is approximately the same as the error we made by neglecting the higher order terms。

And。So what that means is we'll get a suli a ktiya factor from that approximation。

 but that's just going to be a polylo in one over that error。

 and that error per gate was about capital delta squared8 squared。

 so it's a polylo factor of one over capital delta squared eight squared from the suiv a ktaya factor。

 or if I again rewrite that by substituting in the way capital delta scales are time step。

 then it's a polylo factor of an argument which is similar to to this quantity。

 although it's got the eight squared and the spacetime volume squared but it's divided by delta squared instead of delta。

 but at any rate up to a log factor， the circuit size that we need scales like the spacetime volume squared。

And so this is the nice result that we wanted， it shows that we don't know how to do it classically。

 but quantumly we can simulate the time evolution。Even when we have many。

 many qubits at a cost which just scales polynomially in the number of qubits and in the evolution time。

In fact， we can systematically improve this。好。We could do that in the following way。

 these are called Suzuki trotter higher order approximations we canceled the linear terms by approximating the exponential of a sum by product of exponentials。

 but there was some quadratic terms that survive when the terms are non commmuting but we can put together a more clever sequence of these。

Elementary operations are the form E to the minus Iha delta such that we get further cancellations。

 in fact， if we wanted to cancel the quadratic terms。

 it's a fun exercise to show that we can simulate E to the minus Iha delta。

With a product in ascending order in time and then follow that with a product in descending order in time and that causes all the quadratic terms to cancel and so the remaining。

Arror is going to be a order delta squared h cubed in that case and you can even go further than that and get higher order cancellations get the cubic terms to cancel and so on and every time you do that you pay a price in circuit size if you want to cancel to higher in higher orders each time you increase the order of the cancellation that blows up the circuit by some constant factor but anyway that allows you to reduce。

The factor of spacetime volume to almost linear or as close as you want to go to a linear in the spacetime volume and and there are other even more clever approximations that。

Have a scaling， which is actually linear。In the spacetime volume。So that's pretty nice。

 we can with a quantum computer simulate the evolution of some chunk of space time at a cost。

 which is essentially the volume of space time that we're simulating。So why is this significant。

 well， it's an indication that our quantum circuit model really is powerful enough to describe the way nature really behaves。

Because we think the way nature really behaves is that it evolves according to some Schchrodinger equation。

If we have some initial quantum state and we let it rip， there's some Hamiltonian that describes。

It's dynamics。And nature knows how to make the system evolve according to that Schchrodinger equation。

 our if our computational model is sufficient powerful that it can simulate anything that nature does。

 it should have the ability to simulate that evolution and we've seen that indeed we can efficiently。

Polynomial in the volumeum and in fact， linearly， if we're clever。

Simulate the evolution with our quantum computer。Now。

That's a little bit of an exaggeration what I just said goes beyond what we really know。About nature。

 Vis a VR computational model for several reasons。Well， first of all。

 there was the issue of approximating a continuum by lattice， which I already made reference to。

What physicists use to describe nature at a fundamental level is what we call quantum field theory。

And。In quantum field theory。There are really an infinite number of degrees of freedom。

Per unit volume。 So if I wanted to describe what's going on in a quantum field theory exactly in principle。

 I would need an infinite number of。Cubbits in some fixed spatial volume and of course we'll never be able to do that with finite resources if I wanted to capture the way the quantum field theory behaves exactly。

I need an infinite number of qubits per spatial volume we're not going to do that we're going to introduce this lattice spacing。

 introducing lattice spacing of causes and error， but like I said。

 we think at once the lattice spacing is small compared to the scale of some physical process that we're interested in。

We can make that error small。There are further issues。

 quantum field theory is described by a local Hamiltonian。

But the terms at each lattice site actually don't have bounded norm。

 as we assume that was important for getting our approximation that we could bound the norm by H。

And that's just not true in quantum field theory， the degrees of freedom are like harmonic oscillators。

 which and the operators acting on them have unbounded norm。But we think。

It's a good approximation to truncate that infinite dimensional Hilbert space at each lattice site by a finite dimensional one and introduce only a small error。

 and what makes that work is that we're interested in studying processes at some sufficiently low energy。

As the energy increases， then we need to keep track of more and more unit volume because then we're considering processes in which we have shorter and shorter wavelength and we need to capture the very short distance physics better and better to describe that and we might also have fields which are highly excited at each lattice site in that case。

 but the expectation is that at low enough energy， our quantum computer would be able to make a good approximation to the evolution。

Now the things that I've just said， I don't know how to make precisely rigorous。

 the rigorous discussion is， as I presented， we consider a lattice system with qubits on all the lattice sites or they could be higher dimensional systems。

 but finite dimensional systems。At each lattice site and and a local Hamiltonian not necessarily geometrically local。

 although that's usually what we're interested in and each term in the expansion of the local Hamiltonian has bounded norm and in that case as I've。

Argued and tried to convince you we can use a quantum computer to get a good approximation to the evolution at a reasonable resource cost。

 whether that's good enough to really describe nature is not a fully closed issue quantum field theory in particularly in three spatial dimensions which is what we're really interested in is a difficult subject to make mathematically rigorous and lower dimensions there's been more progress there。

And then the even bigger issue， which really is a serious issue， is what about gravity？

Because when we take gravity into account of。There is evidence physicists have uncovered that we can't necessarily describe the dynamics as geometrically local。

Still， there are some reasons to believe that we can approximate the dynamics accurately using some of the same tools as in quantum field theory。

But it's really an open question， whether our quantum circuit model is powerful enough。

Two in general。Approximate accurately， the evolution in a system in which quantum gravity affects。

Are important。Well the question is either， well the answer is either yes or no， yes。

 the quantum circuit model is powerful enough and that would be a very pleasing answer because it means we'd be able to use quantum computers eventually to deepen our understanding of quantum gravity。

 which I actually think will happen， it may be a while but I suspect that will be able to answer questions about quantum gravity and quantum field theory using quantum computers that would just be too hard to answer if we were limited to classical computers。

But there's another tempting possibility that maybe the quantum circuit model is not powerful enough to describe evolution in quantum gravity。

 and that would be very exciting because it would suggest that the quantum circuit model hasn't yet fully captured the full computational power of nature。

 it may be that in that case， quantum gravity effects would allow us to do even more powerful computation。

 which would go beyond what we can do with quantum circuits。

My own prejudice is that that's not likely that the quantum circuit model。

 as we've been studying it in this course， is adequate for describing nature adequately with。

Reasonable resources， but we just don't know at this point。All right。

 so now I want to turn to the other task I mentioned。

Which is estimating the eigenvalues of a big matrix in particular。

 the physics perspective on this would be。There's some local Hamiltonian。

And we would like to measure the energy。Okay， if we have some input state。

In our quantum computer that we prepared somehow， never mind how for now， we'll come back to that。

We would like to perform a projective measurement of the energy。In doing so。

 we'll find the value of the energy and we will prepare in the quantum computer the corresponding energy eigen state。

 and then once we have that energy eigen state， we would be able to compute we could be able to ass simulate measurements so efficiently computeutable observables and learn about the properties of that energy eigen state。

Classically， this is a hard problem， we think because again。We're talking about really big matrices。

 matrices of exponential size， so what I want to argue is that we can do such measurements of the energy。

 such estimates of energy eigenvalues。With resources on a quantum computer that are polynomial in n polynomial in the number of qubits。

 polynomial in the system size。And I've already more or less told you how to do it。

 the idea is to use phase estimation。As mentioned in one of the previous lectures。

 we use a circuit like the one I've crudely drawn here， I apologize for my hand drawing。we。

Are going to simulate time evolution up to time， which is。A here I put it over here。

There's some fixed time which I'm now calling capital T and we're going to simulate for the evolution according to our time independent Hamiltonian now some fixed H for which I want to measure the eigenvalues。

 we're going to simulate the evolution e to the minus Iht for various times。

 oh I think I made a mistake here， I wanted to say one2 four these are supposed to be powers of two for multiples of capital T12 four。

And。Let me get that before I forget。8 up to2 to the m minus1。For summon in your M。And。

What we're going to do is prepare a superposition of all those possible values of T so it's。

A sum over。Ebit strings。Like we've talked about before in this register that records the time。

And then we're going to do evolution evolving by。E to the minus Ih capital T。

 but then raised to the power little T， so there's some unitary。

 which is e to the minus Ih capital T。And we can consider the teeth power of that and that's evolving that's this guy E to the minus I H T。

 And so we evolved for a time which is conditioned on the value of T in this worksops。

 I guess I should go back to my。Presentation mode here。嗯。

So we evolve for a time which is conditioned on the value of T in this time register。

And then I do the quantum Fourier transform and I measure this。Register。

 the time register in the computational basis。So in effect， I'm doing a frequency measurement。

And as we discussed， when we went through how phase estimation works。If I measure the。Mmbit string。

KM minus1 km minus2， blah， blah K1 k0， so you can think of that as a particular integer ranging from zero to the m minus1 what we're doing is projecting out the component of this input wave function。

Which has an eigenvalue for the operator U， which is the exponential of 2 pi I k over2 to the M。Okay。

And at least。It may be that the energy eigenvalue， of course。doesnn't terminate after mbits。

 but we at least we'll get an estimate of that energy eigenvalue to this many bits of accuracy well I explain that when we went through phase estimation so this is just an application of phase estimation。

 which remember allows us to estimate eigenvalues of a unitary operator and we're using it to measure the operator e to the minus ih capital t。

Okay。And here I'm just reminding you that for each one of the qubits in the time register the least significant。

 the next most significant and so on， this procedure where we conditionally evolve，For。H。Tea。

Repetitions of the unitary operator T that's realized by conditioning a single application of U on the least significant be bit u squared on the next。

 u fourth on the next and so on。Okay。And so what that's going to enable us to do is to measure the energy modo2 pi over t because we're really measuring the eigenvalues of e to the minus Ih times capital t。

But if we already know of。Something about the energy or can make a guess。That it's in the range。啊。

From zero to two pi over capital t or between。Hm。Two successive and values of。2 pi over capital T。

 then we can estimate E。Two Mbits of accuracy。Okay。

So what we would do is there's its incoming state Psi。And in effect。

 this is a projective measurement of the energy。So if we repeated this procedure many times。

And each time we get some value of k。If we made a histogram of the results。

 it would have peaks corresponding to each one of the。Eigenvalues of the energy。

And so the positions of those eigenvalues would tell us our estimate of the energy。

And the height of the peaks， that is how many times that particular value was found。

 that would be a measure of the。Inter product squared of the incoming state with that。

Energy eigen state with the observed energy eigenvalue。Okay。

So that's how we would use the quantum computer to measure the energy。And now。

 let's consider how costly this procedure is。Well。What we need to do is simulate time evolution and we've already talked about the cost of doing that。

 okay？So that tells us how to do the hard part of the circuit I just showed you。

 which is the conditional evolution。By。For time tea。

And so we already know the answer for that the largest evolution time that we're going to need to consider is two to the m times t we're going to be considering all possible evolution times from zero to。

Two to the m minus1 times capital t and we want， let's say we want to get M bits of accuracy so that our measurement of。

The frequency register at the end is really giving us。An estimate of the energy to an accuracy。

 which is2 to the minus M where there are M qubits in the time register。

 then we would like or at least it'll be sufficient to have the error。

In the longest time evolution that we considered to be less than2 to the minus M。

And so remember how the circuit size that we found for time evolution。Scacales。

With the evolution time and the error， it went like h squared。

 which was H being our bound on each term in the local Hamiltonian。The spacetime volume squared。

Divided by the error。And in our case， we want to consider T。

 which is some fixed capital t times 2 to the M。So this t squared becomes capital t squared times 2 to the 2M。

And we want to have an error。Which is2 to the minus M。

 So we'll be sure we'll get our Mbits of precision in the end。And so altogether。

 that's going to scale like。N squared the number of qubits times 2 to the 3M。So。

We can say that the resources we need to estimate the energy scale。Polynomally in the system size。

Even if we're trying to attain an accuracy， which goes like one over some power of the system size。

So in other words。We want to get M bits of accuracy。

 so we want the accuracy of our estimate to go like 2 to the minus m and let's say we want that accuracy to go like one over the number of qubits to some power。

 which I call C here。Well how big a circuit do we need well this2 to the 3M here。

 that's the cube of2 to the M， so that's n to the C cube。

And then we also have this factor of n squared。From the way we simulated the time evolution wasn't the optimal way。

 but it's enough to prove the point that the circuit size that we needed to estimate the energy。

Is polynomial in N in the number of qubits？I have the n squared coming from the volume。

 I have the n to the 3C coming from getting good enough accuracy。

 but it's bounded by some power of n。Okay。But they're still catch。If we're going to estimate。

Particular energy eigenvalue and by doing so prepare the corresponding energy eigen state。

 we don't want to have to run this over and over again an exponential number of times。

 let's say we're trying to find the ground state energy which we often are we want to find the energy of the lowest state。

Then if the inner product， if the overlap of the initial state psi on which we conducted the measurement with the ground state is exponentially small。

 then we would have to run this procedure and exponential a number of times before we'd ever find。

That eigenvalue。Okay， so if we want to only have to run it a polynomial number of times。

 we're going to want the that inner product。To not be smaller than one over a polynomial of the system size。

Now that doesn't sound too hard， but it iss not necessarily easy。

Because we have an exponentially large hilbert space， dimension 2 to the end。

 If I just prepared some random state， its overlap with any fixed pure state would be exponentially small an M would go like 2 to the minus M。

 That wouldn't be good enough。 That would mean I'd have to run our energy measurement。

Exponential number of times to find any particular state i'm interested in。

 including the ground state， so I want to have a way of preparing an initial state which has a better overlap with the ground state than exponentially small。

We wanted to at least be no worse than one over polynomial in system size， small。ok。Well。

 there's a general procedure that we can try to give us an initial state。

 which has a large enough overlap with the ground state。It doesn't always work。

 but sometimes it does， at least it's a general procedure we can try。

And this procedure makes use of the quantum adiabatic theorem。And I won't go through the details。

 you may have learned about it and of course， on quantum mechanics in the past。

 but let me just tell you what the assertion is。That if a Hamiltonian changes very slowly。

As the state is evolving。Then under conditions， I'm about to tell you。

If you start out with a good approximation to the ground state of the initial Hamiltonian。

 the Hamiltonian slowly changes and you evolve according to the Schchrodinger equation of that slowly changing Hamiltonian。

 and eventually you reach some final value of the Hamiltonian。

 what the adiabatic theorem says is that the final state will be a good approximation to the ground state of the final Hamiltonian。

ok。If we evolve slowly enough， and I have to tell you what it means to evolve slowly enough。

 if the Hamiltonian changes too quickly， then it won't necessarily work。

So let me just repeat the picture again。嗯。Well， let me say how we're going to apply this。

They's some Hamiltonian and we want to measure its ground save energy。ok。

So we know how to measure energy。We just need to prepare a state which has。

OverLp with that ground state， which is not unreasonably small。

We don't want it to be worse than one over polynomial。Ideally， we'd like it to be better than that。

 like a concert。So here's what we do。 We start out with some Hamiltonian， which is。

An easy one to find the ground state。It might be a Hamiltonian that doesn't have interactions among the qubits at all。

 like all the you know， it could just be a sum of。Poly operator Z for。

For all of the qubits and then we know the lowest energy state would be that each one of those z' is equal to minus1。

the way a physicist would say that is you just put a bunch of spins in a magnetic field and to find the lowest energy state。

 they all want to line up with the magnetic field so we start out with this easy Hamiltonian。

Where we know what the ground state is and we can prepare the ground state in。

The quantum computer very easily。It just all spins up。我。Computational， you know。

 just a product of computational basis states。And then we simulate using our Schchrodinger evolution algorithm。

The evolution of the state for a Hamiltonian that slowly changes， it starts out with this H easy。

 which is the Hamiltonian whose ground state was easy to construct。

 and that was the state that we started with， and it slowly changes along some path and it winds up with the Hamiltonian we're really interested in。

 I called it H hard， meaning that its ground state energy is might be hard for us to compute。And now。

 according to the adiatic theorem， if the change in the Hamiltonian along the path was slow enough。

Then we'll wind up if we started out with a good approximation to HEZ。

 we'll wind up with a good approximation to HR。So the simplest thing would be just like a linear interpolation between the two。

Where at time zero， the Hamiltonian is h easyZ and then we'll let the time slow increase from zero to capital t and as it does so H easyZ turns off linearly in team in time while H hard is turning on and finally when we reach little T equals capital T H E is gone in the Hamiltonian is H hard。

 it doesn't necessarily have to be this linear interpolation。

 the adiabatic theorem will be happy for any path from the initial Hamiltonian to the final Hamiltonian。

Except now I have to say what it means。For the evolution。

To be slow enough for the Hamiltonian to change slowly enough。

As the Hamiltonian is changing at every point along the path。

There's some ground state and there's a first excited state。

The state with the second lowest energy eigenstate。And the difference between those two energies。

 the ground state energy and the first excited state， that's called the energy gap。

It just means the spacing between the two lowest eigenvalues and as we evolve。

 the Hamiltonian as the Hamiltonian changes along the path from each easy day chart。

 that gap is going to change because both the ground safe energy and the first excited state have energies that change in time。

There's some closest approach between the two eigenvalues， which is called the minimum gap。

 I'm going to call that capital delta。So here。Is to find the way I just said as。The time little T。

Evolves， or as we evolve along the path from each easy day hard parameterized by little T。

 varying from zero to capital t， the minimum value that's attained by the difference between the ground state energy and the first excited state。

 that's what I'm calling deelta the minimal gap。What the adiabatic theorem says is that if I choose T large enough。

Capital T controls how slowly with increasing little T the Hamiltonian is changing if I choose it large enough。

 large enough means greater than some constant divided by a power of the minimum gap。Then will。

Stay in a good approximation to the ground state if we started out in one。And。Why is it true， Well。

 I'm not going to prove it for you or anything it can be proved。

The intuition is that if there's a gap between the ground state and the excited state and the system is slowly changing。

you have to excite the system from the ground state to the first excited state by giving it a rap。

By introducing some energy， the energy is coming from whatever。Mechanism。

 whatever agent is causing the Hamiltonian to change in time， and in order to jump in energy。

 we need to push the system at a characteristic frequency。

 which is a good match between the difference in energy between the initial state and the final state。

And when the Hamiltonian is changing very slowly， there's very little support in its Fourier transform at frequencies。

That then match the minimum gap and so there's very little amplitude for exciting the system from the ground state to the first excited state or to any of the higher states as well。

And so it just stays stuck in the ground state。Okay。So。

That means that our procedure for preparing the ground state will work well enough。If the energy gap。

 the minimum energy gap， never gets smaller during this excursion of the Hamiltonian from the easy Hamiltonian to the hard Hamiltonian。

Then one over some polynomial in the system size。If it's one over the polynomial， the system size。

Then we have to evolve for a time which is。Has a sufficiently large value of capital T。

 but that's going to be polynomial in the system size。

 and we know we can evolve for a time which is polynomial in system size at a cost which is polynomial in system size because that's what I showed you in our discussion of simulating time evolution governed by the Schchroinger equation。

So one over polynomial in end gap is okay。At least it means that in polynomial time on a quantum computer。

 we'll be able to prepare the ground state。But if it gets worse than that。

If it gets super polynomially small at some point during the excursion， then it's going to fail。

Because then we would have to evolve for a super polynomial time。

 if the gap gets exponentially small and and at some point。

 then to avoid jumping across the gap to stay in the ground state with reasonable amplitude we would have to evolve for an exponentially long time and that has an exponentially high cost in terms of circuit size。

OkayAnd in fact， we think this is exactly what goes wrong in some cases。

That there are some Hamiltonians for which it's hard， even with a quantum computer。

 to estimate the ground state energy to an accuracy that goes like one over polynomial and n。

I'm going to explain in the next lecture why we think it's true。Well。

 I can tell you now what we're going to discuss in the next lecture。

iss that the problem in general of estimating ground state energy to one over poly and accuracy is a QMA hard problem if we could really do it efficiently we'd be able to solve efficiently every problem in QM the quantum analog of NP and almost everybody agrees that's very unlikely so that means there must be at least some local Hamiltonians for which quantum computers can't。

Solve for the ground state energy can find the ground state energy in。Polynomial time。

And since we know how to do the evolution， we know how to do the phase estimation what must go wrong。

Is that the state preparation fails that's just too hard to prepare an initial state that has an overlap with the ground state。

 which is。No worse than one over a polynomial。In some cases。Oh， that's just got to be hard。

Now that's a little discouraging， it means there are some local Hamiltonians for which preparing the ground state is hard even with a quantum computer。

What does it tell us about the conjecture or the expectation I was advocating just a minute ago that we should with a quantum computer be able to efficiently simulate any process that occurs in nature if we can't even with a quantum computer construct？

The good approximation to the ground state of some local Hamiltonian well。

 that doesn't necessarily mean that we fail in our goal of simulating physics the lesson you can draw is that if there's a Hamiltonian such that。

Finding the ground state or preparing the ground state is a QMA hard problem then。

The preparation of the ground state isn't going to occur in nature。

 there won't be any natural process that will'll be able to prepare that state。

 so if we're interested with our quantum computer in simulating things that can really happen in the physical world。

 then reaching the ground state of one of these QMA hard local Hamiltonians isn't a problem we need to solve because that's not something that occurs in nature。

now。You know what states can be prepared in nature is ultimately a question about cosmology and the early universe。

 and so that gets us into a lot of interesting issues。But。You know， the。

High level observation is that there are things that we can't do in polynomial time on a quantum computer。

 we beating the quantum computer。Operators， the quantum engineers， then。Nature can't do it either。

 and so that doesn't mean that we're not able to efficiently simulate nature。Okay。

 so I guess that will do it for today。 just one more lecture to go。 and the next time I will。

Talk more about this idea。That finding the ground state of a local Hamiltonian。

 estimating its energy to one over polynomial and in accuracycur is a really hard problem in general。

 a QMA hard problem。So until then， thanks for stopping by。



![](img/ee0a992e0912b6e1c494ca7b10173dd9_2.png)

It's。It's been fun as always。I look forward to seeing you next time in the meanwhile。

 how take care of yourself and be well。I'll see you soon。

