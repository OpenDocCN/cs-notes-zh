# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p15 -15-Ph CS 219A Lecture 13 Black Box Model.zh_en -BV1KgffBoEUc_p15-

![](img/8d3be9f5647fc06420874ef6b948cc38_0.png)

Okay， hi， welcome back， Quaum friends。 Welcome back to physicsy Comp Science 2，19， a。

 great to see you again。 It's been too long， but the good news is。😊。

We're going to have a lot of fun today。 We're getting into the。

Cool part of the course where we'll start to talk about quantum algorithms。

And let me remind you where we left off last time。嗯。Now， of course。

 we would like to be able to say as a rigorous statement。

That quantum computers are more powerful than classical computers。

 We really don't know how to prove that from first principles， even though。

We strongly believe it's the case， otherwise I wouldn't be taking。

 or I wouldn't be teaching this course and you probably wouldn't be taking it。

There are several kinds of evidence that we can marshal indicating that quantum computers can do things efficiently that are too hard for classical computers。

One is， we know of some algorithms。That。Theoretically would run efficiently on a quantum computer if we can manage to build a large scale quantum computer。

 which I think we will， and we don't know how to solve those problems efficiently with classical computers。

There are also what are sometimes called relative by speedups or oracle speedups I'm going to talk about that today this is a model in which we can make rigorous statements about the separation between quantum and classical and it's an instructive model。

 but it does not by itself tell us that there are。You know， beginninggning1。

Applications and then applications of quantum computing。That are exponentially faster than。

Algorithms running on classical computers。And there are also polynomial speedups。

 not exponential speedups that we can talk about where， for example， a quantum computer。

Solves a problem in a time which is the square root of the classical time。

 so that doesn't directly relate to the big question of whether BQP is strictly larger than BP。

But it's nonetheless interesting and we'll get to that， but when I want to talk about today。

Is relativists relativized quantum speedups in the oracle model。

So what is this oracle model well the idea is that there's some black box and it computes a function and we don't a priori know what that function is。

 we might be given some promise about the function that it has a certain structure but we're not told everything about it and our task is to。

嗯。Find out some property of the function to learn something more about it。

And the way we keep track of the complexity in this setting is that all that we keep track of。

 the only thing we measure is the number of times we have to evaluate the function in order to solve the problem and we're interested as we increase the size of the input to the function。

How the number of queries， evaluations of the function。嗯。How many are needed to solve the problem。

 How does that scale within。 So all these terms mean more or less the same thing。

 Sometimes we call the。Function a black box， meaning we don't necessarily know anything about its structure。

S we call it an oracle， same idea。It does something magical， which we don't understand， but we can。

Query it with a。An input to the function and it will spit back the answer and query model again means the same thing because we think of asking the black box questions and it gives us answers。

 we don't know how it does it。But。The measure of complexity will be how many times do we have to ask the black box a question so why is that an interesting model to consider it I mean one way way you might think about it is that there's some subroutine and we don't really understand how it works。

But we know we can call it if we're running a program。

And maybe we have to pay every time we want to call that function and so we want to keep track of the cost in terms of the number of times we have to pay the fee for making a query for evaluating the function。

If what we're really interested in is the gate complexity for solving some problem。

 you know the total number of gates in the circuit model that we need to run the algorithm。

 at least the number of queries will give us a lower bound on that because therell release be one gate inside the black box and so the number of gates we would need if we open the box will be at least the number of queries。

And sometimes we get insights from this model about complexity outside or beyond the black box model。

 it might be that it turns out for some particular task， it really is possible。

For the box to be instantiated by some efficient circuit。It's also important though。

 that the additional processing that we have to do when we get the answers from the box is something we can do efficiently in the query model we don't worry about that just like we don't worry about the complexity of the box itself。

 we just want to know you know from a。If you like information theoretic perspective without keeping track of how hard the computation for us is。

How many times we have to query the box to get enough information so we can find the property of the function F that we're looking for？

So the way I'm going to distinguish quantum from classical in this setting。

IsI'm going to consider boxes which can be queried in two ways。

 you can either query them with computational basis states in which case the box behaves in a classical way。

I u。Essentially give it a bit string and it gives me an answer back。

But the quantumness will come in because we will allow queries to the box which are superpositions of those computational basis states and what we're interested in is whether that ability to query in superposition gives us some additional computational power。

That's what we want to study。Okay， so to get started。

 suppose we're talking about a function that has an n bit in PP， say it's a boolean function。

 so it takes n bit。To one bit， we could also consider functions that have many bits of。Output。

 but for now， let's just suppose it's Boolean。 Now， I would like to have a model of my box。

 which I can think about quantum mechanically。 But when we ask it a classical question。

 it gives a classical answer。And so we'll be thinking about this unitary transformation。

 we've kind of talked about this sort of thing before。It's going to have。

Two registers that it acts on it this unitary acts together altogether together on n plus1 qubits。

So x is n qubits， y is one qubit and if the。States， x and Y are computational basis states。

Then what this unitary is going to do is you're conditioned on the value of x。

 it's going to flip the value of y if f of x is equal to1 and not if f of x is equal to zero。Okay。

 so if we set y to zero。Then we query the box with x and then we can read out in this one bit answer register the value of Fx。

But what's going to make a quantum is we won't necessarily consider the queries to be computational basis states。

So let me give you an example。Of a problem that we can study in this setting。

 first discussed by David Deutsch back in the 1980s。

And now I'm going to consider about the simplest thing we can。

 it's a function that takes one bit to one bit， okay？So if you know the value of f of zero and f of1。

 then you know everything about the function， right？

So you could find out everything about the function。

If you query the box twice in the classical setting。

You query it with zero and it tells you f of zero and you query it with  one and it tells you f of 1 and that's it。

But let's suppose that I don't need to know everything about the function。

 Let's suppose that the future of civilization。Rest on whether I can answer a question about this function namely。

而。F of0 and f of1 the same value， in other words， are both inputs map to the same value。

Or are they mapped to different value。 So if they're mapped to the same value。

 I call it a constant function because for any input。It gets mapped to the same value。

 a constant value and balance just means that the outputs0 and1 occur an equal number of times when I consider all the possible inputs to the function that's what I mean。

By balance， and let's suppose， you know， that whatever the box is doing and we don't know what it is。

 it's something really complicated。So it takes 24 hours。

To get an answer back when you query the box and we desperately need to know whether the function is constant or balanced。

 we don't really care。What the value of f of zero and f of1 are。

 all we want to know is whether those two values are the same。

We only want to answer the constant or balance question now in the classical query setting。

Tough luck。 We're going to have to query the box twice because each time we query it， we got the。

Value the function for one particular input， and that's not going to tell us whether the function is。

Balanced or constant。We can't afford to wait 48 hours。

 the world is going to explode if we don't get the answer in the next 24 hours。

 so we just got to do it with one query。So what happens if we can query and superposition。

 does that make things better it does now with a。Quantum query with a superposition of。

Computational basis states one query will be enough to answer the question。

 whether the function is constant or balanced and civilization can be saved。So how does this work？

Well they they're kind of two tricks that come in the first i'm going to call the phase kickback trick we'll see a more general version of it later and the idea here is that answer register the second register。

We can， if we choose its input state to be an appropriate superposition。

 we can make it into a phase oracle， so the information about whether f of x is equal to zero or f of x equals one comes back as the relative phase of different query states。

So how does that go Well let's consider the poly operatorator x you remember what that is it flips the bit。

 it takes the state zero to the state one state one to the state zero let me consider x raised to the power a where a is a bit so that either that means the identity if x is equal to zero。

And it means x if sorry， it means the identity of a is equal to zero。

 and it means x if a is equal to1。So you won't disagree with this statement that x to the a acting on a basis state。

 either zero or1。I can write as Y x or a， if a is equal to zero， is the identity。

 it doesn't do anything。If a is equal to1， it's going to flip the value。Okay。

So let's see what happens， I think you know this if I consider the superposition。

 either the uniform superposition or the superposition with a relative phase of the basis state0 and1。

 well， they are in fact， the eigenstates of the polyoperator X。你。

Uniform superposition with a plus sign when x x is an eigenstate with eigenvalue 1 because0 and1 change places and that doesn't change the uniform superposition。

 but when 0 and 1 change places the minus superposition flips phase so the minus state0 minus one properly normalized is the eigen state of x with eigenvalue minus10 plus1 is the eigenstate with eigenvalue plus one。

So I can write that this way， x to the a acting on the basis states plus or minus。

 give me minus1 to the a basis states plus or minus， because of course， if a is equal to zero。

 this is just the identity and neither plus or minus or affected， but if a is equal to1， then。

The states plus and minus have opposite eigenvalues。Okay。

 so I'm going to make use of this nice property of the minus state that we get a phase when xx。

Because what are remember what our。What our Oracle is going to do。

 it's going to x or whatever is in the second register with the value of f of x where F。Is the。

Seccrret function that the black box evaluates。 So if I query with x。

 the computational basis state and minus in the second register。Well。That's that x or with F of x。

 that's the same thing as x raised to the power F of x。

And that's going to be the same thing as minus1 to the f of x because this is the eigen state of x with eigenvalue minus1。

So the minus superposition isn't affected by the query， minus goes to minus。

 but what happens is the phase of the state is affected。

We either get a minus one if f of x is equal to one or we get no phase。

 just one when f of x is equal to zero。And that's now I'm done with the second register。

 we're not going to need to talk about it anymore， it's not really affected by the query。

 and so we might as well just say that what our box does。

Is when we query it with computational basis state x。

It modifies the phase of that computational basis state。

B minus1 to the f of x either flips the phase if f of x is equal to1， or it leaves the phase alone。

If F of x is equal to zero。Okay， now， of course， if I give it a classical query in the X register。

 who cares changing the phase。Isn't going to。Change anything， it's just an overall phase。

But the way I can take advantage of that phase kickback is by querying with a superposition of two values of x。

So that's what we do we consider now remember now i'm just talking at the I'm forgetting about the answer register now。

 which is set to minus one and what that managed to do was give us this face kickback。

And now I'm going to query。With the superposition of0 and1 in the X register， okay？

And the0 is going to pick up a phase -1 to the F of 0。 The one is going to pick up a phase。

 -1 to the F of 1。 Okay， so up to an overall phase。

 this is going to be the state0 plus  one with appropriate normalization。

 if the function is constant if F of 0 is equal to f of 1。If the function is balanced。

 then the two phases are different， so up to an overall。Phase， perhaps a minus1。

 this will be the state minus if the function is balance。

 so it's plus if the function is constant minus if the function is balanced。

 so now after just that one query， I can measure in the basis， the Xigen state basis。

 the plus minus basis， if I get plus I know it's a constant function and if I get minus。

 I know it's a balanced function。Now， the way we defined our computational model， you remember？

As we said， I think。That we're supposed to make our measurements in the computational basis。

 but that's okay before I measure in the computational basis， the01 basis I can apply the had mark。

That's the guy that maps the x basis to the z basis。 so it'll take plus to0 minus to1。

 So measuring in the plus minus basis， that's the same thing as first applying the hadard and then measuring in the computational basis。

 So that's what I do。And we've seen that there's a difference between the quantum and classical queries with classical queries we've got to have two to determine if the function is constant or balance with quantum queries。

Just one， so civilization has been saved。By use of quantum queries。

So let's try to make it a little more interesting by having a variable input size。

 So now I'm going to consider it's called the Doutsche Josa problem。

Which was discussed in the late 1980s by those two guys， Richard Jo and David Deutsch。

Now we're going to have a function which maps and bits to one bit。

 It's not an arbitrary function this time。 there's going to be a promise about it。

 we're going to be told that either one of two possibilities is going to hold。

Either F is a constant function or it's a balanced function。 What does balance mean here， Well。

 now there are two to the n possible input values of x。

So what I mean by balance is that for half of those input values of x。F of x is equal to zero。

 and for the other half， F of x is equal to1， zero and 1 occur。Or the same number of possible inputs。

 So altogether two to the n minus1 values of x。Will be mapped to zero by the function。

 and altogether two to the n minus1 values of x will be mapped1 by the function。Okay。

So what do you think we're going to do， I bet you can guess we're going to query in superposition。

We're going to use phase kickback like we did before， Okay， so we're going to。嗯。

I'm talking about I'm still talking about a Boolean function it's taking n bits to one bit。

 so we fix that answer register that one qubit in the state minus now we get a face kickback。

We are going to prepare the uniform superposition of all possible values of x that's actually quite easy to do。

We just apply a hanaard to each one of Nqubits where the qubits are initialized at zero。

And that's going to give me for each qubit， the uniform supervision of zero and one。

 and altogether that means every bit string occurs with the same amplitude。

 one over the square root of two to the n。And now we query the box and now the phases get modified in this superposition of all these values of x。

We got a superposition of all of two to the n values of x。

 I'm going to call it x equals0 to2 to the n minus1 since I'm thinking of those bit strings as binary representations of integers。

Which are expressed in terms of n bits， so that can be any integer non negative integer from 0 to2 to the n minus1。

And that。Comput basis state x in this uniform or rather this coherent superposition is going to pick up the phase minus1 to the f of x。

Okay， so what I'm going to do now is I'm going to measure all the qubits in that plus minus basis。

Okay。Another way of saying it is I apply that hadamamad to each one of the Nqubits。

 I'm calling it a bit wise hadamard or hadamardd H tensor n times。

Single qubit gate applied to each one of the Nqubits。Now， if the function is constant。

Then that means that I get the same phase every time it's just minus one to that constant and so this is again just the superposition of all possible bit strings。

 which is the same thing as the superposition of zero and one for each one of the n qubits。

So the plus state tensor1 times。And then when I do the head mar on each one of the qubits。

 that's going to be mapped for each qubit to zero。So in the case where the function is constant up to a phase of plus or minus1。

 depending on whether the constant value of f is0 or1。We're just going to get the state of all zeros。

 okay， that's in functionist constant， but what happens if the function is balanced。Okay。

 this is I just told you， this is what happens when the function is constant what if it's balanced so what I want to know is what is the amplitude。

For getting the outcome of all zeros。In the case where the function is balance。

That is I'm going to do the query and then I'm going to apply that bit was hatard and then I'm going to measure in the computational basis state。

As we've noted， that's the same thing as saying I'm looking for the inner product。

Of the state after the query with the product of pluses for all the qubits。

 because the hadamard acting on zero gives a plus。And that plus is just the superposition of0 and one。

 so the product of all the plus is again， that's just the same thing as one over the square root of two to the n。

Some uniform sum without any relative phases of all the possible bit strings。

 or if you like all integers， y equals 0 to2 to the n minus1。

I'm interested in the inner product of that。With the state I have after the query。

And the phase kickback has occurred， so it's this inner product。And of course， these。

Some is here going to collapse， I'm only going to get terms with x equals y。

 I had two factors of one over the square root of2 to the n， so I got a1 over2 to the n。

And then I have a sum of all the phases， minus1 to the F of x。

 And that's going to be true in general， no matter what F of x is。 But if it's a balanced function。

 that's going to be 0 because。Half of these phases are going to be plus one and half of them are going to be minus one。

Right half the values x f of x is equal to 0， and the phase is plus one for half the values of x F of x is equal to1。

 then the phase is minus-1。 So all the phases cancel okay。So。

TheAfter I've done that bit was Hanniard， the overlap with the all zero state。

In the case where the function is balance is zero。So。I query。I use the face kickback trick。

 I had a mar and I measure if the function is。Constant with probability one。

All the outcomes of zero for measurements on all N qubits。And if the function is balanced。

 then I'm never going to get the outcome where all the measurements are zero。

 I'm going to get some other bit string， never all zeros， always something else。

So with just one query。Okay， we either get all zeros and conclude the function is balanced sorry constant it's constant when we get all zeros or we get something else。

 and then we know the function is balanced。 All right。

 so just one query answered the question pretty cool。And it doesn't depend on n at all。

 The number of queries we need because it's always one， no matter。

How large the input size for the function？Now， if we had only deterministic classical queries。嗯。

In the worst case， you know， we would choose。One value of x after another and query the box。

If we were really made really bad choices， the worst case。

It would be even if the function is balanced， I just happen。Two to the n minus one times in a row。

To query with the value of x that gets mapped to the same value every time。 either0 over one。

 So I still don't know in that worst case， after2 to the n -1 queries after I've input half of the possible values of x。

 I still don't know for sure whether it's constant or balance。

 And I have to finally get to2 to the n -1 plus1。 and then because it's a balance function。

If it is balanced， I can't get the same value again。

 I have to get the other value and then I know it's balanced。And if I get the same value once again。

 then I know it has to be constant so that's if you like a exponential separation since in the worst case I need an exponential number of queries。

 if they're classical queries whereas in the case of quantum queries just one query was enough。

 buts that's kind of fake it's better to think of it as a randomized algorithm。

Where I choose random values of x to query with， and then I'd really have to be exceedingly unlucky to choose queries two to the n minus one times in a row that always get mapped to the same output so what's really going to happen is I can query some not huge number of times。

And if I get the same value every time， then I can be very confident that the function is really constant and that didn't just happen by accident。

 And if I ever get。A response when I query that's different from the previous response says then of course I know the function isn't constant and I'm done。

 I can declare that the function is balanced because I't promised it's either constant or balanced。

So。You know if you， if you if the function really is。

 I think that's what it says here is if the function really is balance and I query k times。

And then I'm going to declare either constant or balance based on whether I got the same answer every time or not。

 the unlucky case in which I fail is when just by accident， I got the same answer k times in a row。

 even though the function is balanced， but every time I do a query， if it's a random query。

 I have probability one half of getting zero， one half of getting one for me to get the same value in k queries k times in a row。

 the probability of that is just the probability of getting either all heads or all tails when you flip a nonbiased coin。

K times， that's a probability of1 over2 to the K -1。

 So I don't know if to choose K to be very large to have a small probability of getting the wrong answer in this randomized algorithm。

 So in other words， I can solve the problem efficiently。

Either in the randomized classical setting or the quantum setting in the quantum setting。

 I'm right every time in the classical setting， I can easily make the probability of failure quite small with a number of queries which。

I not very large and doesn't actually depend on the value of n。

 it just depends on the error that I'm willing to accept。All right， so that was kind of instructive。

 but not terribly exciting。Now let's try to make it more interesting and see if we can find。

An exponential separation in query complexity between quantum queries and randomized classical queries for some black box problem and I'm going to tell you such a problem it's called Simon's problem after Daniel Simon。

And he proposed it and analyzed it。Back in 1994。Now I'm going to consider a function which takes n bits to n bits instead of a boolean function。

And I'm going to give you a promise。Well， first I'm going to tell you one version of the problem。

 then I'm going to massage it a little to make it into a decision problem in case you think that's important。

So let's say I'm promised that this function is actually two to one。So every output has。

That occurs has two pre images。But furthermore， it has a special structure。

Which is that X and y are mapped to the same output。If and only if。

The bit wise X or of X and y is either zero， which of course means x equals y or equal to some bit string a。

 So what I mean by that notation， these are actually n bit strings x Y and a。

 I say that X X or y is equal to a， I mean that's true bit by bit that x0 x or y0 x or is just addition mod2。

 so maybe I should just say plus to save myself。From saying X or all the time。

 and it means x1 plus oh y1。Is equal to a1 x2 plus y2 is equal to a2 and so on。 So in other words。

 a is equal to1 if the bits X I and Y I are distinct and equal to0 if they're the same。

And our problem is to find a and we want to do that with as few queries to the function as we can。

Okay。So how hard is it classically well just if you want to think about decision problems i'll note that we can turn this into one we could say that actually the promise is that either this is a one to one function so every output has just a single pre image or it's two to one with the structure that I described here。

 which I'll say is the function has some period a just meaning that I can add a to the input and。

Get the same output。Okay。Well， the problem formulated as a decision problem is in what I'll call NP supero。

 that means oh is an oracle， it's this box that we can query this particular function concerning which we are given the promise。

And。We'd like to solve the problem but what if somebody gives you a witness Can you check the solution to the problem Well。

 that's pretty easy because I could be so kind as to give you the value of a and then even in the case of classical queries。

 it would be easy for you to check that a and zero both end mapped to the same value and then you will know that a is indeed the period of the function with just two queries two classical queries are enough to check once you have the witness。

But I'm going to argue that Simon's problem is not in BPP。Supero that with access to this oracle。

 you can't distinguish the two to one case with this structure and the one to one case。

Except with exponentially small probability， or I should say one half plus something exponentially small because you could always make a random guess and。

Find the answer with a success probability of one half。Um。That。You can't。嗯。

Except with an exponentially small probability。Get the answer with a polynomial number of queries。

 that's what I mean when I say it's not in BPP super O。嗯。So why is it so hard with random queries？

What can we do， we're just going to the best we can do is just randomly query some number of times。嗯。

So suppose we query altogether together k times。And we choose a random value of x each time。

So if F is actually two to one。We'll solve the problem， even only if we are so lucky。

That two of the values of x that we queried with happen to get mapped to the same value of F of x。

 they happen to be pre images of the same output value per f。And。Well。

 that's not very likely because。If I just consider one pair of inputs in particular。

X and Y x gets mapped to f of x。What's the what's the probability that？

Y different from x will get mapped to that same value。 Well， there's only one possibility。

 it would have to be x plus a。 I'd have to be so lucky as to choose Y is equal to x plus a。

 I don't know anything a priori about what a is。So。Of course， I don't， I didn't mean。

Two to the n minus one， I think I meant one over two to the n minus one。

 the probability of getting lucky for a pair of queries。If I query altogether k times。

 well you can think of that as I now have a sample of k choose two candidate pairs of input values of x for each one of those pairs I have this small probability of getting lucky so the probability that we're successful in K randomized queries isn't going to be larger than the number of。

Pairs of K queries。Times the probability of success for each pair。

 which is just1 over2 to the n minus1， so that's less than k squared over2 to the n。

So I could actually choose k to be exponentially large。

 like say2 to the1 half n times one minus epsilon， and this probability of success would still be less than two to the minus epsilon n in that case。

So even though for some fixed epsilon， I'm considering an exponentially large number of queries。

 the probability of success is going to be exponentially small in n。

And that's why I say it's not in BPppP supero。Don't have a way of solving the problem with a reasonable success probability with a reasonable number of queries。

But I'm going to argue that Simon's problem is in BQP superro， that is if we're allowing。

Quantum queries， we can solve the problem efficiently。 That is with a number of queries， which is。

 in fact， just linear and n。 We can solve the problem with high success probability。

 And so on that basis， I can make the claim that relative to this oracle O。

 that's what I mean by a relativized separation relative to this oracle。

 when that oracle is available to be queried， there's a separation between。

Being able to solve the problem with classical queries and quantum queries。

 I need an exponential number of randomized classical queries。

 but I can do it with a polynomial number， in fact， a linear number and then。Of quantum queries。

Within this。Black box model， we can make the statement that quantum computing。

Interpreted as the ability to query and superposition is more powerful than randomized classical computing。

All right。So now I have to tell you what that quantum algorithm is and how that works。Okay， so。

 you know， you kind of know the routine by now， I guess I want to query with a uniform superposition of all the computational basis states like I did in the Deutsch Jo problem I'm not going to use phase kickback this time。

So I guess if you want to think of it as a circuit diagram。It looks like this。

We have the register that we query in， we have a register where the answer appears。

They're both and bit registers， so in order to query with a uniform superposition of all possible inputs。

 I can imagine starting with all zeros。And doing the it was hadardd。And then now。

Box is going to apply a unitary， which is going to add the endbit string F of x。

to an endput an endpi end bit answer register this time and this is just a symbol for measurement I'm going to want to measure not in the computational basis after the query but in the complementary basis if you like the head emred basis or equivalently I'm going to do a bitwise head emred on all the end bits and then measure in the computational basis。

 okay。So let's see what happens。So we prepare this uniform superposition of all queries。

 uniform superposition of all values of x， we set the answer registered to zero。

And then we do the query， and so for each input value of x。

 F of x is going to be written on the second register。So now。We get an entangled state。

A massively entangled state of。Of the two registers。

 some overall two to the n values of x x tensored F of x in the output register， okay。

And then what I'm going to do is， if you like， just trace out that answer register。

 I don't need it anymore， I can throw it away。And then we're going to do this measurement in the head of our basis in the query register。

Now I said you can trace out or measure， you know， as we've discussed before。

 you could think of tracing out as being like measuring but throwing away the outcome。

We can imagine if you like that we actually measure the value of the answer register。

 we get some particular F of x0。What we're really going to have。

In the input register is a mixture of。All the。Different estate that can be obtained for different。

Orthgonal basis states of the output register。 So we're going to have a mixture of states。

One corresponding to each possible value of F of x。

 But let's look at one particular of those states because the thing is。

Our algorithm isn't going to really care about the value of x sub zero。

 it's going to work the same way， no matter what the value of x sub0 is。

 even though we know what it is we're not going to use that information so whether we measure or not doesn't matter so we don't need to know what it is so we don't really need to measure and we will still have decocoherence between you know the different values of that answer register。

F of x， and so we can imagine that we're looking at any one of the。

Pure states in an ensemble representing the mixed state that we have in the answer register。

hy don't I just say we measured okay， we measured and we got a particular value F of x0。

 so what does that mean？Well， let's suppose the function is two to1 or if you like。

 let's consider the version of the problem where the task is not to determine whether it's two to one or one to one。

 but to find a， we know it's two to1 we'd like to find a， of course。

 if it's two to1 and we can find a and then once we find a we can easily check that a is correct because now it's like the what I said before we have the witness and we can just query twice to check that it's really right that F of zero is equal to f of a。

U what we're going to get now is because there are two values， it's a two to one function。

 which are mapped to each one of the outputs that occurs。嗯。

Corresponding to f of x0 in the answer register are the two pre images of F of x0。

 which are x0 and x0 plus a and because we started out。

With a uniform superposition of all the inputs， we're going to get this uniform superposition of the two pre images。

X0 and x0 plus a。I guess I wrote plus a instead of。X or or O plus。

 but you can just think of that as bit wise arithmetic mod too。

 I should change that and make it into an O plus whoops。Where are we here。Okay， no。

 I've already done that。嗯。Oh， I did that too， okay。All right。

Now this is what we have in the answer register we oh sorry in the input register in the query register。

 we threw the answer away， we're not going to need it。So now what。

 well we could measure in the computational basis， but that really wouldn't do us any good at all because。

The outcome would just be one of these two computational basis states each occurring with a probability1 half。

 either x0 or x0 plus a。But。What good is that going to do？嗯。

It's not going to tell me anything about A， I didn't know anything about A to begin with。

X0 and x0 plus a by itself， that's not enough to tell me A， if I knew them both， of course。

 then I would know a。Measuring the computational basis isn't going to tell me both it'll tell me one or the other。

 so I don't want to do that。Instead I'm going to do what I said here。

 I'm going to measure in the the complementary basis。

 I'm going to do the bit wise had mard and then measure so we want to see what happens in that case。

Well， let me go back， Im going to。Just introduce a little more notation， which is kind of handy。

So what does a ahead of Mar do？Acting on a single qubit。

 well let x be one of the computational basis states， it's either zero or1。

 remember it takes zero to zero plus one and it takes one to zero minus one。

So let me write that in this fancy way。X， either 0，1 gets mapped 21 over squared to 2。

0 plus -1 to the x1。So in other words， if x is equal to 1。

 I got a relative minus sign here and if is equal to zero， I don't。

And here's another fancy way to write it。I have the one over square root  two。

 and now I'm summing over the computational basis state， which can be either zero or1。

 and I can write the phase as minus1 to the x y， I'm going to get a phase only in the case in which both x and y are1。

ok。So now let's do the same thing when we do the bitwise head tomard acting on some bit string。

So let's consider this n bit string， one of the computational basis states。

 each one of the qubits is either a zero or one as indicated by the。X I's。

And now I do all the head ofards and let's use this little formula to see what happens then well for each one of the head ofs i've got some it's acting on some basis state X and that's going to be mapped to。

one over squared to two times the sum over the two that should be y subi。

 two possible values of y sub I and the phase is minus1 to the X I Yi， there's a nontrivial phase。

 only one to both Xi and Yi are one， and it's a tensor product of n such states。

And if we just expand that out。I've got。All these possible bit strings occurring here。

And the overall phase associated with the output state y n minus1 y n minus2 blah blah blah y1 y 0 is going to be minus1 to a power and that power just sums up all these phases I can or takes gives me the product of all these phases。

 So it's minus one to the。X0 y0 times minus1 to the x1 y1 plus times minus1 to the x2 y2 and so on。

 and I'm just writing that as minus1 to the x dot y， and by x dot y。

 I mean this bitY inner product of n bit strings， the sum of X I Y I I going from0 to n minus1。

And I might as well say mod too， because all I care about is whether that's an even or not。In aature。

 the number of times that that strings x and y collide， in other words， whether that's。

Even a odd parity is the only thing that matters because I'm it's minus one raised to this power and if that's an even number that's one and if it's an odd number it's minus one okay？

Okay。So now this just repeats what I just told you。

Acting on some computational basis state for Nqubits， the bitwise Hadmar is going to give me this。

Okay。And。Now I want to consider what happens when the state that I'm acting on is this。

Coherent superposition， this uniform superposition of two computational basis states。

The two pre images of a particular output value for F of x， namely x0 plus x0。嗯。XRA。Okay。

 so now I've got this one over2 to the n over two here and I've got this extra one over squared root to two here。

 so I'm combining those together to give me oh， yeah that's right to give me a prefactor of one over2 to the n plus1 over2 so I'm still summing y over all of the two to the n possible values but now I tab the sum of two different phases from x0。

 I get minus1 to the x0 dot y and from x0 x or a I get minus1 to the x0 x or a。t y。And now， you know。

 the magic of interference can appear， some answers are going to happen with some non zero probability and some are going to happen with zero probability because those two phases cancel。

If one's a plus one and the other one is a minus one。

 that value of y is not going to appear with a non zero coefficient in the superposition。Well。

 let's factor out minus1 to the x0 dot y， and then what remains is the sum of 1 and minus1 to the a dot y。

Okay。And that's either going to be zero。If if a dot y is mod2 is equal to plus1 or it's going to be two if a dot y is equal to zero mod2。

If A do y is even in other words， it's going to be2 if a do y is odd we're going to get zero so what survives。

 so since it's two that's going to get rid of vector two here so now that denominator is2 to the n minus one over2。

And then occurring in the superposition。Are all the values of y such that a do y is equal to zero？

So if you like the language we could use。In the sense of a binary linear algebra。

Is that what occurs are all the values of y which are orthogonal to a。

 such that that bitwise inner product。Of a with y。Is equal to zero and the values for which it's equal to one。

嗯。They occur。't they don't occur。 The coefficient is0 in that case。 Now。

 there's also a phase that depends on why that's where the x0 comes in。

 But I don't really care about this phase because what I'm going to do now is measuring the computational basis。

And that phase associated with each value y isn't going to affect the probability distribution。

For those measurement outcomes， in fact， what is that probability distribution with probability zero？

We get the values of y which are not orthogonal to a， the one such that y。 a is equal to one。

And with uniform probability， all occurring with the same amplitude squared。

 namely1 over2 to the n minus1 are all the values of y that are orthogonal to a such that a dot y is equal to  zero。

So that's what we learned by running one query， we randomly sample from all the values of y that are orthogonal to a。

That's giving us。A。Some information about A， that's giving us some information。

Not enough information to know， not yet。So we run that same routine multiple times。

Every time we're sampling uniformly from all the values apply Y that orthogonal today。

After we've done it enough times with high probability， we will have n-1 values of y。

 which are all linearly independent in the sense of， you know， binary linear algebra。

 all linearly independent values。Which are all orthogonal to a so you can think of this as you know we're trying to find a vector。

In the sense of binary linear algebra。Whi is in an n dimensional vector space。

And once we know n minus one linearingly independent vectors that it's orthogonal to。

 then that vector is uniquely determined。And in fact， it's an easy linear algebra problem。

 I'm not going to go through the details of this since it's straightforward and I think you all know how to figure it out。

That once you had those n minus one values of y， which are all linear independent oral orthogonal a。

 there's an easy matrix inversion problem for finding A and you're done， you found a。Okay。

 and if in the decision problem， you know， if you find a in the case where the function really is two to1。

 then of course you can check that A really is the period of the function to verify that the function really is two to one。

好。Furthermore， as I guess I said already， but I'll repeat is that you don't need a large number of trials to have a high probability of finding these n minus one linearly independent values of Y that we need to uniquely identify A。

So in fact。Each time you run another query and do the measurement， in other words。

 each time that you randomly sample from the strings that are orthogonal to a。

 if you haven't already found a set of n minus one linearly independent vectors。

 then you're going to have a probability of at least one half。

Of finding one which is linear independent of what you've already found， okay， because every time。

You find one。Well， just think about it you you once you have n minus two values of y。

 which are all linearly independent。In this n minus one dimensional space。

 which is orthogonal to a then of the strings that remain。

Half are linearly independent and half are linearly dependent。And when you have when you so far。

 you've only found。You know n minus3 of the values of y that are linearly independent。

 then you have an even better chance of finding one that's linear independent of what you already have found the next time you run the algorithm。

 so you have a probability at least one half every time。Of finding a vector or orthogonal to a。

 which is linearly independent of the ones that you've already found。And so really。

If you run the procedure， M times， you're sampling from the strings which are orthogonal to a altogether M times。

You will have。Not yet solve the problem if somehow accident。

 you haven't yet succeeded in finding n minus one linearly independent values that are orthogonal to a。

 but the likelihood of that happening。Is actually not no worse than the probability that when you toss a coin。

M times that you have。That know， you failed to get heads。Let's see， it's smaller。

you're trying to get heads with heads corresponds to the winning possibility that you find something linearly independent of what you already have。

 you have probability at least one half of doing that if you were exactly one half that would like be like the probability that an unbiased coin comes up heads and you want to be sure that you get heads and minus one times。

 then you're done， but to have a high probability of getting heads at least n minus one times。

It's enough to toss the coin a number of times， which is some constant times in。

And then the probability that you haven't managed to get heads n minus one times is going to be off on the tail of a Gaussian distribution and the probability of failure will be very small。

So the number of queries that we need to solve the problem to identify A is linear and end in the quantum case。

 in the case where we can do these quantum queries。

 which enables us to prepare this uniform superposition of the two different inputs that go to the same output。

 and then because we can also measure， we don't want to measure in the computational basis。

 if we measure in the complementary basis， the head and our basis。

 then we get information about A and we don't have to do it many times。So that's the story。So。

You have seen。That we can solve Simon's problem。With order N queries。

 some constant times n number of queries。If we're allowed to do quantum queries。Okay。

But if we're limited to randomized classical queries， or if we can only query with the。

Computational basis states with bit strings。Then we'll need an exponential number of queries to identify a with a better than exponential。

A success probability。And so that's the basis of my statement that。

We have a strict conclusion of BPP relative to Simon's Oracle in BQP relative to the Oracle。

 or if you like， there is an oracle such that BPP。And BQP are distinct。TheQP being larger。

Relative to that oracle。So that's nice。 It's a remarkable result。 It's very simple。

To see how it works， it works through the magic of。Interference。

That the values of Y that we don't want don't occur because of interfering amplitudes。

 the values of y that we do want that are useful to us occur。

 and we do it enough times and we have all the information we need。Now， remarkable as it is。

 does it have any practical applications， well actually not that I know of？

To find an real application。We would like to have some instantiation of Simon's Oracle。

 some function that we could really evaluate so that we could operate the black box ourselves。

And such that the problem is still hard classically。

 even when the structure of that function is known。Okay。And what we don't know。

 at least I don't know an example like that。Of course， ideally。

 we would also want it to be some problem that we care about the answer for some practical reason。

And because Simon's algorithm has no obvious real world applications。

 his original paper was rejected when he submitted it to a conference。

 even though it's a brilliant paper。But the problem and its solution turned out to be very inspiring and in fact led to another black box problem for which we can prove analogously to what we did today。

 a separation between quantum and classical query complexity。

 and that one does turn out to have practical applications。

So that's what I want to tell you about in the next lecture。So until then。

 good to see you again until next time， take care of yourself。Stay healthy and see you again soon。



![](img/8d3be9f5647fc06420874ef6b948cc38_2.png)