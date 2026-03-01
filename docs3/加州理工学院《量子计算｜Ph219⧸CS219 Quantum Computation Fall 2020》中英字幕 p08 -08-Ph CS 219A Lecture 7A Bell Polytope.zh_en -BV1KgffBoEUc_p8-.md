# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p08 -08-Ph CS 219A Lecture 7A Bell Polytope.zh_en -BV1KgffBoEUc_p8-

Hello there， all my quantum friends。Welcome back to computer science physics 219 a it's good to see you again。

 at least I like to imagine that you're right there on the other side of this computer screen and I hope that's true。

Because we're going to have a lot of fun today continuing to explore。

The wonders of quantum entanglement that。Delightful feature of the quantum world， which is really。

The secret sauce that underlies the topic of this class， quantum computing。

 why we're interested in quantum computing is。That nature。Harbs， amazing resources。

Which allow us to speed up the solutions to some computational problems very dramatically。

And quantum entanglement is a big part of the story。Of how nature manages to pull that off。

So let us resume our discussion begun last time。Of。



![](img/7dd544283990f2b328a2ca415cc6c62e_1.png)

Balinequalities。Last time we talked about the CHSH inequality。

It applies to classical strategies and a two party cooperative game。

Strategies that can be carried out by parties who might share randomness， random bits。

But don't share quantum entanglement。And we saw that quantum strategies where the parties playing the game actually do have shared quantum entanglement。

 which they can measure。Enables them to violate the chHSH inequality。

 they have correlations among their measurements which couldn't be realized in any classical model in any classical strategy and we discussed how these violations of the chHSH inequality have been confirmed and experiments they really are。

Remarkably， part of the story of how nature behaves。

And we're going to continue with the discussion of Bell inequalities today。

 What I'd like to do today is put what we talked about last time in kind of a broader context。

 We're going to wind up revisiting the CHSH inequality， deriving it again。 but from。Fresh viewpoint。

 there will be a lot of to do to set up this new derivation in that regard， in that regard， it's。

More complicated than the story I told you last time， which was actually quite simple to convey。

 but I think looking at the CHSH inequality from this broader context is enlightening。

 it deepens our understanding of how quantum correlations are different from classical wantss。

What I'm going to talk about today is not discuss mostly in the lecture notes that are available。

 the type notes that you can access from the course website。

 of course you will have the slides that I'm presenting and I hope they give a selfcontained account of what I'm trying to tell you and of course you have this video as well so。

I hope everything will be clear if you do want to read further about the topic from a point of view similar to what I'm presenting。

 I am recommending or advising you of a reference。And I'll put that on the course website too。

 so you can find it if you need it。I'm going to be assigning today。Another problem set。

 which I'd like you to hand in by the end of next week。Actually， one of the problems has to do with。

Quantum teleportation， which we haven't gotten to yet and won't by the end of this lecture。

 we'll discuss it in the next lecture， but I hope in plenty of time。For that problem。To make sense。

 and in any case， you can read about that topic in the chapter four notes if that'll help you get started。

So let me remind you of what we talked about last time， the CHSH inequality。

 it applies to a situation where there are two parties， Alice and Bob。Who。

Each receive one of two possible inputs， which I had called a and A prime for Alice B and B prime for Bob and then。

Alice and Bob after receiving that input， but without any communication between Alice and Bob。

 between when they receive the inputs and when they produce the outputs are to output either a plus one or a minus one。

And we derived an inequality。That applies to the correlations between Alice's output and bos。

 So what I mean by a here is either the plus one or the minus1 that Alice。

Finds as an outcome if she has the input a and when I'm saying a prime。

 I mean the plus one or minus one that。嗯。AlS outputs when she gets the input a prime。

 I hope that's not too confusing， but anyway， we talked about that last time。

And what the inequality says is that this particular linear combination of correlators。

 expectation values of products of Alice's variables and Bob obey this inequality。

 the absolute value of the sum of these four quantities but with this telltale minus sign in the last term。

 I has to be less than or equal to two， and then we talked about how this bound can be violated in quantum theory if Alice and Bob share not correlated bits but quantum entanglement and in particular if they have a maximally entangled state。

Of two qubits， Alice has a qubit and Bob has a qubit。Where they're entangled。

 we computed that if they choose right just the right measurements for their qubits labeled by A and A prime for Alice。

 B and B prime for Bob， that this quantity can actually be as large as。Two square root of two。

 it can't be any larger。So the CHSH inequality says that in the classical setting。

Where there's no shared entanglement has to be less than or equal to two。

 there's a Cyilcin inequality which applies to the case where Alice and Bob have shared entanglement and are measuring quantum observables。

 which says it can't be greater than two root2， it actually can be as large as two root2 if they use just the right strategy as we saw。

And what I was saying at the end last time， well， actually before I get to that。

 I'll remind you of one other thing we did last time， which is that I can rephrase this。

In the language of a game， we can imagine that Alice and Bob are playing a cooperative game。

 they're trying to help each other win and the object of the game is for Alice and Bob to produce outputs that are correlated in a way that depends on the inputs they receive。

In a particular version of the game that corresponds to this CHSH inequality， the goal of the game。

 what they need to do to win is to output the same value if。

The and of Alice's input bit and Bob's input bit。Is zero and output different values if that end is one so in other words they're supposed to output the same value。

 either both plus one or both minus one， if the inputs are00，01 or 10， but if the inputs are 11。

 then they're supposed to output different values。That's how the game is played。

 they're not allowed to communicate between receiving the inputs and producing the outputs and what the CHSH inequality says is that the best possible strategy。

If they only have shared bits。Correrelated bits， rather than a shared entanglement allows them to win the game with a success probability no larger than 3/ quarters。

If we average uniformly over the four possible values of their inputs。The corresponding quantum Bo。

 the Silson Bo， says that their best。Success probability for winning is larger。

 one half plus one over two Ro two， better than 85%， classically they can only get up to 75%。

So a quantum strategy using entanglement is better。

Allows a higher probability of successfully winning the game than in the case where they don't share entanglement so they can use entanglement to do something that they couldn't otherwise do。

And as I remarked at the end last time， I'd like to now look at be inequalities。

 the CHSH inequality is an example of be inequality from a somewhat more general point of view。

 I'll be changing the notation a little bit， but I hope it will be clear。

And from this more general point of view， we may get a deeper appreciation of what beinequalities are about。

 how classical and quantum behavior differ from one another。

So I'm going to consider a somewhat more general story。

 I'm still going to assume that there are two parties。

 I'll continue to call them Alice and Bob from time to time。

 one could tell a story about more parties， but it's already interesting enough。If we stick with two。

And generalizing beyond that CHSH setting， I'll now suppose that Alice gets an input which doesn't just take two possible values。

 but some number m a possible value， some finite number。And same for Bob。

 I'll assume just to keep things simple that the number of possible values for the input received by Alice and Bob are both the same that there are M possible values in the quantum setting。

 we can think of that as an instruction to perform one of M possible measurement。

 so I'll call it a measurement setting with that picture in mind。

And then they produce outputs and let's suppose that the output has the possible values。

 it was two in the CHSH setting， but it could be more some finite a number and you can think of those if we imagine Alice and bond performing measurements as the possible outcomes of the measurement it might be a PVM if we're in the quantum setting with。

Altogether V POVM elements， so there are V possible outcomes for the measurement。And。

The situation can be characterized by some conditional probabilities。

 the probability that Alice and Bob produce outputs X and Y when they receive inputs A and B。

And what I'd like to understand is what we can say about constraints on such probability distributions that apply under different conditions and in particular in the classical setting where there's no short shared entanglement and where there's an additional locality constraint。

 which I'm about to explain。Um， on Alice and Bob that Alice。

 because there's no communication between Alice and Bob。

 Alice doesn't know what input Bob receives when she produces her input and Bob doesn't know what。

Input Alice receives when Bob produces his output。And anyway， though。The general setting is that。

We just have some。Probabilities of outcomes for each of the possible settings and we'll call any such。

Probability function， probability for x and y， given A and B。

 a state in some space of possible states and we're trying to characterize。Those states。

 what can we say about the probability function？Now。

 one thing we know is that probability summed to one。So for each choice of the settings， A for Alice。

 B for Bob。If I sum over the probabilities of all the values of the outputs X and Y。

 I better get one。And that tells us how many。Parameterters we need to characterize one of these states。

It means that for each value of A and B， the probability doesn't take v squared。

 well there's a constraint on the v squared probabilities on the outputs x and y namely this sum up to1。

 so the total number of parameters that I need to characterize this function is the product of the number of settings and that's m for Aliceis and m for bo。

 so m squared altogether and then the number of。Real parameters characterizing this function for a fixed A and B is the number of outcomes。

UV squared， except I subtract one because there's one constraint that the probability sum up to one for E A and B。

So for example， if I were talking about a case like CHSH where there are two possible settings and two possible outcomes that space of states would have dimension 12。

 real dimension 12， because they're altogether together four possible settings。

 two for Aliceison two for Bob， and there are four possible outcomes。

 but their probabilities sum to1， so it's four times  three， which is 12。

Now let's bring in that locality idea。We'll say that we have a local configuration。

If there is some definite value of Alice's output X for each of the possible inputs that she could receive and that that definite value does not。

Depend on Bob's input B so now we're bringing in the idea we discussed last time that if we really had the complete description。

 then we wouldn't really have to speak about probabilities at all that we could assign a deterministic。

Outcome to each one of the possible measurements or each one of the possible inputs that Alice could receive。

And we're furthermore bringing in the idea of locality。That Alice doesn't know what Bob's doing。

 what input he's getting， and in the case where we have a deterministic configuration。

 she has to produce her output without knowing Bob's input。And。The same thing for Bob as for Alice。

 for each possible input， if we're in a local configuration。

 that's the word I'm using to describe these deterministic situations。

Bob produces some definite value y for each possible input and that value y depends on the input that Bob receives。

 but it doesn't depend on the input A that Alice receives。And I'm going to speak of a local model。

 sometimes people call this a local hidden variable theory。

As a model for this probability distribution， this conditional probability， P of x Y given A B。

In which。We assigned some probability to all those local configurations。

 So if we really knew everything about the description of the system。

 we'd be in a deterministic situation。 That's what the local configurations are。 But in fact。

 we're considering some convex combination of those local configurations assigning some。

Probability to each one of them。Probabilities， of course， non negative numbers， suming to one。

 that's what I'm calling a local model or a local hidden variable theory。

 and be inequalities are constraints。On such local models， on these probability functions， P of X， Y。

 given A B， that apply under the assumption that we're in a local model。

 a convex combination of these local configurations， where each configuration is deterministic。

 Alice produces a definite。Um， output and Bob produces a definite output where Alice's output only depends on her input and Bob's output only depends on his input。

Okay， sorry， lots of text on this slide， but let let's go through it。

So this just repeats what I just said in the first couple of lines。

We have this probability function for each choice of analysis setting and boB setting。

 there's some probability for their outputs， X and Y， given A and B。And by a local model， I mean。

 we assign some probability to each local configuration。

 and I'm going to speak of the local region in the space of all states in the space of all of these。

Probabilities， P of X Y given A B。As the set of。Points in the space of state。

 which can be obtained as a convex combination of those local configurations。 Here。

 I use the word convex whole。 That just means it contains all the points that can be obtained in the state space by giving some。

Non negative probability weight to all the local configuration such that those weights sum up to one。

Okay， so those are all the possible states that we can get in a local model。

And it has the property geometrically of being what we call a polytop a polytop and that's just a word for a convex hall of points in some vector space。

 so I've drawn a picture here， it's an octahedron don't pay too much attention to that I just wanted a polytope that I would be able to draw。

And it has a set of vertices， this octahedron， which are my attempt to draw the local configurations in this space of state。

 these are points in the space of states， and then the convex hull of the points in this particular。

Example， it's altogether six points of vertices of the octahedron by the convex hall， I mean。

 the entire interior of the octahedron that's everything that I can get inside， which is obtained by。

Taking a convicx combination of the vertices okay， now I've also drawn an origin at the center of my polytope。

And you can just think of that as the special case where we give equal weight to all of the local configuration so that somewhere deep inside the octahedron and I like having an origin because I'd like to think about。

A vector from the origin to the point in the state space representing one of these local configurations。

 Here's one such vector， which I showed in red。Going from this origin to one of the vertices。

 which corresponds to a local configuration。Okay。So now let's imagine we're experimental physicists。

In my case， takes a lot of imagination， but let's suppose that's true。

 And we have some experimental setup。In a two party situation。

 Alice and Bob are doing experiments together and they have buttons they can push to choose their settings。

 They have an apparatus which has a dial， which produces an output。

 so by doing many runs of their experiment。They will be able to determine this function。

 the probability about puts X and Y given settings A and B。

They do the experiment enough times and they'll know that function with。

High statistical accuracy and with high confidence。And now we'd like to answer a simple question。

Theyve determined the state and their experiment， they know P of X Y given AB。

 is it in the classical region， can it be explained by one of these classical local models。

 a local hidden variable theory， is it indeed a convex combination of the local configurations。

 the deterministic configurations。Well， that's not such an easy question to answer in general。嗯。

It would really help out our experimentalist， well I guess I'm the experimentalist， so are you。

 it would help out us experimentalists a lot。If we knew some inequality。

That we could easily check such that。If that inequality is violated。

 then we know for sure the state is not in the classical region， okay？And。Given this inequality。

 I can check it against my data pretty easily and see whether it's satisfied or not。

And if it's not satisfied， then I know there isn't any classical model that can explain my data。

 okay？That's what we mean by a bell inequality， just such an inequality， which， if violated。

 means no classical model can account for this function， P of X， Y， given A B。

And well you can think of a be inequ equality as a hyperplane in this space of states。Where。

What the be inequality says。Is that if。If a point is in the classical region。

 then it has to lie on one side of this hyperplane。And if it's on the other side of the hyperplane。

 then we know it's not in the classical region。And so if we look at our polytope here。

There are lots of ways in which I could choose a hyperplane or plane in my drawing。

 such that the whole octahedron lies on one side of the hyperplane。

But if I want to make my inequality as tight as possible。

 then what I should do is line up that plane。With one of the faces of the  Otahedron。

If the inequality says that the。In order to if in the classical region。

 my state has to be on let's say， the right side of some plane。

 if that plane is lined up with one of the faces of the octahedron。

 I made the inequality as tight as I can I can't move that plane any further to the right。

 then the inequality wouldn't be valid anymore because there would be。

Points in the classical region on the other side。Of the hyperplane。

 So the tight bell andequalities correspond to the faces of this polytope。And， in fact。

As I'm about to try to explain。So far， I've described the polytope as a convex combination of vertices。

 The vertices being local configurations。 But there's another way to completely characterize the polytope in terms of all of its faces。

 So if we knew。Bell inequalities for each one of the faces。

 then the points in the state space thats satisfy all of those beinequalities would have to be in the classical region。

Right。嗯。I hope that's clear， coming back to the octahedron， I could characterize the octahedron。

As an example of a polytope by saying it's the convexhu of the points which are the vertices。

Of the octahedron， but I could also say that all the points。

 a point lies in the interior of the octahedron， if and only if。It lies on the right。

Side on the correct side of a set of planes where。There's a plane lined up with each one of the faces of the octahedrons。

 they're all together eight faces and so I can choose eight planes。And。

If I know it's on the correct side of each one of those eight planes。

 then I know for sure we're in the classical region in the convex Hall。And so。

One way of characterizing our。Classical region， our classical models is to say we give some probability weight to teach each one of the local configurations。

Another way is to say that the classical model obeys a complete set of bell inequalities。

 there's a be inequality for each one of the faces of the polytoe。Okay。

 so there's a nice way of describing a plane。In。A D dimensionsal space。Well。

What I really mean is a d minus one dimensional hyperplane。

And it can be characterized by saying that it's normal to some vector。

 at least if that hyperplane doesn't go through the origin， okay？

And so I can choose some normal vector to the hyperplane。And I can choose its normalization， in fact。

 so that all the points in my hyperplane， which I had drawn in this light blue color here。

Obey the condition there are all the points in my space here we're thinking about this state space such that the inner product。

 the dot product of the point I and the vector beta is equal to1 okay so that means that the component well you know what it means it means the component of the vector of beta。

Palm。That's up。Perpendicular to the plane has a fixed value and that defines the whole hyperplane。

So if I wanted to talk about the half space that lies on one side of that hyperplane。

I guess I said hyperplace here， but you know what I meant， it's hyperplane。

Then and which side do I want， I want the side that contains the origin because the origin is always。

In my polytope， remember I've defined the origin to be a particular convex combination at the local configurations。

 so being on the same side of this hyperplane as the origin，Well。

 the set of points that satisfy that are the points such that the points is I in my state space。

 such that the inner product of psi and beta is less than or equal to one。And。

There's a notion of a polar of the polytope， which defines a kind of duel of the polytope。

And it consists of all the extremeal。Half spaces that contain the polytope so again I'm trying to capture that idea that I can describe the polytope as a set of hyperplanes which line up with the faces of the polytope and if you're on the right side of all those hyperplanes。

 then and only then you're inside the polytope。So this polar can be defined by saying it consists of all of the vectors in。

The space， the state space， I'm calling capital Oomega。Such that。

Beta dotsi is less than or equal to one for all psi。And。

The equivalent way of saying that is that the polytope itself can be characterized as the set of all points in the state space such that beta dotsi is less than or equal to one So again the idea is that that satisfied for all of the beta that which are in the polar the different beta you should think of as the different hyperplanes that define the faces of the polytope and this is just the condition that you're on the right side of one of those。

Hyperplanes that defines a face and in order to be in the classical region。

 you have to be on the right side of that hyperplane for all of the faces。嗯。

For all of these extremeal half spaces that contain the classical region。In other words。

 there are lots of hyperplanes such that the octahedron in my example lies on one side of the hyperplane。

 but I can choose those hyperplanes to hug the octahedron line up perfectly with the face。

 and then the only way to lie on the right side of all of those hyperplanes。

 one for each face is to actually be inside the polytope。

And you can see that the polar is actually convex。It has the property that if。我。

Beta 1 is in the polar and beta 2 is in the polar， and that means beta 1 and beta 2 both satisfy this condition for all of the points which are in the polytope。

 but then it follows that a convex combination of beta 1 and beta 2，Also has that property。嗯。And the。

Extremeal points of this。Prial polytope， those are in my setting the local configurations in our state space。

Those actually correspond to dues to faces of the dual polytope。

 the dual polytope you can think of as the set of faces。

 the polytope is the or rather the convicx combination of those faces。And the。

Prial polytope is the convex combination of the。Of the vertices that define the polytope of our local configurations。

And you can see this relationship between the two is symmetrical between the primal and the dual。

 polyte， they dual to one another。就。Don't get too hung up on the fancy language。

 polar and duall and all that all I'm really trying to say is that there are two ways to characterize a polytope。

One is I can tell you what the vertices are and then you can consider the convexhull and the other is to characterize all the faces and if you're on the right side of all the faces then you're in the polytope I've said that enough times by now。

 I guess。Okay。So that's great if we can come up。With that characterization of the polytope in terms of the faces。

Then it's actually easy to check。For each one of the faces。Whether my data。

 my point in the state space， that probability function P of x Y given A B。

 whether it satisfies the inequality or not， whether it's on the right side of the face。

 and if I check all of the inequalities if I have a complete set of inequalities and it satisfies them all。

 then I know it's got to be in the polytope， it's a local model。

 and if it violates any of those inequalities， then it can' to be described by a local model。

 it's not in the polytope。So everything's great， except that it can be a difficult computational problem if I tell you what the。

Vertices are， in our case， the local configurations。

To find that complete set of hyperplanes that define the faces， to the polar。The polytope。

 because that polyte can have lots， lots of vertices。

And there are algorithms for computing the polar of a polytope， but the algorithms have a runtime。

 which grows very rapidly as the number of extremeal points of the primal polytope increase。

So that's too bad。But at least in some cases， and simple cases， we can do the computation。

And find the polar of the bell Potope。 It's been done， for example。

 in the case we discussed in the context of the C， H S H inequality。

 where Alice and Bob each have two possible inputs and two possible outputs。In that case。

 we have altogether together 16。Extreal points， which you can just think of as assigning a definite value plus one or minus one to each of four quantities A and A prime and B and B prime in the language I use to describe the CHSH inequality that's two to the four possibilities。

And remember the state space is 12 dimensional in that case。

 so there are 16 points in this 12 dimensional state space。

 The be polytope consists of the convexhu of those 16 points and。

It's a solved problem to find a description of all the faces of that polyte。

That gives us a complete set of bell inequalities which characterize the polytope if you check all those be inequalities and they're all satisfied。

 then that means that our state is。In the classical region can be explained by a local classical model。

 but it's kind of hard to picture。A。Polytope in a 12 dimensional space with 16 vertices。

 so let's make it a little bit easier。We can reduce the dimensionality by not considering the complete configuration。

 but by trying to capture what's important， the correlations between Alice and Bob with some set。

Of correators。 And just by correlators， I just mean expectation values。

If you want to use the quantum language。Of observables。That tell us how Allison's and Bob states。

Are correlated with one another or how their systems are correlated with one another。And so。

In the special case where there are two settings for Alice， two for Bob。

 and they each have two possible outputs。We'll consider this set of four quantities。

The expectation value of A B， of A B prime of A prime B N of A prime B prime。

 Now I'm going back to the language we use in describing the CHSH inequality。Where by a。

 I mean Alice's。Output plus or minus one when she has input A。And by a prime。

 I mean her output when her input is a prime， okay？Now， if we're in a local configuration。

 that means each of A， A prime， B and B prime have a definite value plus or minus1。

So if you know what the inputs are， you know for sure what the outputs are。And like I said。

There are 16 such exal configurations。But for the set of four correators， A B， A B prime， a prime， B。

 and A prime B prime， there are actually only eight extreal points。

And that's because if I flip the sign of all four variables， A， A prime， B， and B prime。

That doesn't change the correlators because they all involve a product of two of the variables。

 So changing the sign of all doesn't change anything。

 but there are eight different possible extremeal points。In this four dimensional space。

 I went from 12 dimensions to four dimensions， that should be easier。

This four dimensional space where the components of this vector in the four dimensional space correspond to these correlators。

 expectation value of A B of a B prime of a prime B and of a prime B prime。

As governed by the conditional probability distribution P of X Y given。AB。Okay。

So you can understand why we only have eight extreal points in the following way。

If I consider the local configurations， that means A， A prime B and B prime。

 I'll take values in plus or minus1， and now if I take the product of A B， A B prime。

 A prime B and A prime B prime，Each one of the barrry bowls appears twice in that product。

And so minus signs cancel out the product is just going to be equal to one。

And so that means for any local configuration。The values of a B A。

 B prime a prime B and a prime B prime， they're all plus or minus one， but they have to have。

What I'll call even parity， that means the number of minus signs has to be an even number。Either。

Zero or two or four， okay？And in fact， you can write down the possibilities。

For all of the values of the four variables， A B， A B prime， a prime， B。

 and a prime B prime at the externalal points。I wrote plus instead of plus one and minus instead of minus one just to。

Make to streamline the notation and I can either have all pluses or I could have two pluses and two minuses。

And or I could have all minuses， and in the case where there are two pluses and two minuses。

 there're altogether together six possibilities and I listed them all here。

And each one of those is going to determine an inequality which is satisfied by the polar。Okay。

 so the polar。Remember consists essentially it defines all of the planes which have the property that the polytope lies on the right side of the plane。

And。For example， in the case where I consider now I'm talking about the polar， of course。

 in this you know four dimensional space， not in the 12 dimensional space that we started with。

Let's say I'm considering the extremereal point plus plus plus plus。Then the four components of beta。

 if it's in the polar。Have to satisfy plus beta zero plus beta 1 plus beta 2 plus beta 3 is less than or equal to1。

ok。On the other hand， there's also a extremeal point in which I flip all the signs。

 all pluses becomes all minuses， and so now it's minus beta0 minus beta 1， minus beta 2 minus beta 3。

 which is less than or equal to 1。Which I can conveniently write as the sum of beta 0 plus beta 1 plus beta 2 plus beta 3 is greater than or equal to minus1。

So I can combine those two inequalities in this way and it says that a beta is in the polar。Then。

This。Linear combination of the components of beta。has to lie between 1 and 1。

And I can make a similar statement about all the other possible extreal points。Okay。

 so if I consider the extremeal point。Plus1 plus one， minus1 minus one for these four variables， a B。

 a B prime， a prime B， and a prime B prime。Then the corresponding condition on the polar is that plus beta 0 plus beta 1 minus beta 2 minus beta 3 has to be less than or equal to1。

 and then there's also the case where I flip the sign of all the values。Of the。Of the variables， a B。

 A， B prime， A prime B and a prime B prime， and that's where I get the other inequality。

 which is as minus one is less than or equal to this combination。And。I wrote down this inequality。

 this pair of inequalities that corresponds to the exal points plus minus plus minus and minus plus minus plus per A B。

 A B prime， A prime B， and A prime B prime。And this pair of inequalities that corresponds to the exal points where A B。

 A B prime， A prime B， and A prime B prime。Are equal to plus minus minus plus or the signs are opposite okay？

And now those are the conditions for beta to be in the polar。

But what I'm interested in is the extremeal values of beta that are in the polar。

 that's what corresponds to the faces of the polytope。So how do we get an extremeal point， well。

 we want these inequalities to be saturated。In order for beta to be extremeal。Either on the one side。

 the upper bound or on the minus one side， the lower bound。

 So for each one of these four linear combinations in the extremeal case。

 when beta is extremeal in the polar， this linear combination in each one of the four lines will either be equal to plus one or to minus1。

And that means there are altogether 16 possibilities， so over these four linear combinations。

 I've just rewritten them over here。In the extremeal case， each one is equal to plus 1 or minus1。

 I call those values F0， F1， F2 and F3， altogether 16 cases， F0， F1。

 F2 and F3 are allowed to be plus1 or minus1。And those will define values of beta。

 which are extremeal in the polar。 And those are our bell inequalities。

 That's what's going to characterize the faces。Of the。Of our polytop， okay？嗯。So here we go。

 there are 16 choices。For these fs for F0， F1， F2 and F3 for each one of the 16。

 I'm going to get some value of beta， which is extremeal in the polar。

 and that's going to give me a bell inality。So， for example。

If the four values of f are plus1 plus1 plus1 plus1， well to the corresponding value of beta。

 which is extremereal in the polar， I just have to solve these four linear equations where now I have on the right hand side a each equation one and。

One can easily see that the solution is。That beta 0 is equal to 1 and the other components of beta are all equal to zero。

You can see that that satisfies all four equations。1 equals one， one equals one， one equals one。

 one equals one。嗯。And， of course， if I flipped the value of all four。

Components of F instead of plus one had minus one， I'd get a solution。

In which I take this solution and just flip its on。

 So now beta 0 is equal to minus-1 and the other components， beta 1， beta 2， beta 3。A。Equal to zero。

And that gives me two inequalities， and they're really not very interesting， are they？

So what these inequalities say is that。A correator。

If it's inside the polytope has to satisfy expectation of L A B is less than or equal to 1。

 That's this case where beta is equal to 1， but it's also greater than or equal to minus1。

 that's this case where beta is equal to minus-1。And so really all it's telling me is that the expectation value of AP had better be between minus one and one。

But that's really trivial because it doesn't really have anything to do with the locality of the configurations。

 All models have that property。Even if it were a non local model。Then。You know， a in a。

Extremal point in a local configuration is always equal to plus1 or -1。 same thing for B。

 So A B is always equal to plus1 or -1 in a local configuration。 And so in the polytope。

 which is just。Convey's combination of those local configurations it's certainly going to be between minus one and 1。

Okay， so that's kind of automatically satisfied， but we recovered it from our analysis of the polar。

Of the polytope。 and then there are three other cases。 Well， actually， yeah， okay。

 three other cases where。F has。Even pary， where it has an even number of minus signs。

And I listed here plus plus minus minus plus minus plus minus and plus minus minus plus。

 and then I can also get even parity values of F just by flipping the signs of all the components and those are the ones I've listed here and it's easy to check that in these three cases for F。

Each of which remember defines an extremeal point in the polar。

 I get a beta equal to one for one of its。4 components and 0 for the others。

And here I just flip the sign to get these other solutions where beta is equal to minus1。

 and all that's telling us is that we have the same inequality。

The expectation value is less than or equal to1 and greater than or equal to minus one for each one of the four correlators。

 a B prime， a prime B and a prime B prime。So they're all equally trivial。

 not very informative about how to distinguish。The classical models。

 the classical region from non classical models。But we're not done yet because we haven't considered all the values of F。

 we've only considered the ones that have even parity。

 we have to consider the ones that have odd parity as well。H。Okay， so let's do that， let's do that。

So for example， if。I consider F0 equals plus1， F1 equals plus1， F2 equals plus1 and F3 equals minus1。

 then I get a more interesting solution。I solved this set of equations。And I find。

That beta 0 is equal to1。 beta 1 is equal to1 half。 beta 2 is equal to1 half。

 beta 3 is equal to minus1。Well， let's just check quickly that that solution really works。

So for this choice of beta， I need to check。That the sum of the four components equal to plus1。

That's true。Beta 1 minus beta 2 is 0 in this case。 beta 0 minus beta 3 is equal to plus1。 Oh。

 that's good。 F1 is equal to plus1。The beta 0 and beta 1 are equal here。

 so beta 0 minus beta 1 is equal to zero， but then I have beta 2 minus beta 3 that's equal to plus1 fine F2 is equal to plus1。

And again， I have beta 0 minus beta 1 equals0， but now I have minus beta 2 plus beta 3。

 and that's going to be minus1， so this satisfies the four equations with F0 equals 1， F1 equals 1。

 F2 equals1 and F3 equals minus1。So this is the corresponding element of the polar。 It defines a。

Face。For our bell polytope associated with this particular choice。For the extremeal points。

 So what it means is that a classical model will have to obey this constraint。

That the combination expectation value of a B plus ab prime plus expectation value of a prime B minus expectation value of a prime B prime is less than or equal to1 Okay。

 well that's what we saw in the CHSH inequality。And you can also check that if I change the sign of all four components of F and I change the sine of all four components of beta that's still going to solve the equation。

 So another extremeal point， the one corresponding to F0 equals -1。

 F1 equals -1 F2 equals minus-1 and f3 equals plus1， gives me this other value of beta。

 which just is the same as this one， but with the opposite sign that gives me another inequality。

 which says that this linear combination of correlators。

Times  one half is greater than or equal to minus1。

 so together they gave they give the inequality we wrote down last time。

 which says that the absolute value of this quantity in parentheses is less than or equal to2。Okay。

So what are all these other exreal points of the polar， these are other。

Constraints that have to be satisfied by any local model。 Well， there's really no new news here。

 Our polytope has a lot of symmetry。And all of the other inequalities have the same form as this one。

They differ only according to where the minus sign appears here the minus sign was in front of the expectation value of a prime B prime。

 but there's another extremeal point of the polar in which the minus sign is in front of a prime B。

 another in which it's in front of A B prime and another one in which it's in front of A B， okay。

So since we have an upper bound and a lower bound， and there are four places where we could put the minus sign that's all eight inequalities。

We have 16 extremeal inequalities altogether corresponding to the faces of the bell polytope for the correlator。

 and now we've listed them all。There are the eight that are trivial。

 which just say that each correlator has to lie between plus one。And minus1。

 and there are eight which are non trivial， of which the CHSH inequality that we considered before is two of those inequalities because we have an upper bound and a lower bound。

And all the others are just related by。Exchanging the names of the variables。 So， for example。

 if I replace a by a prime。Then I would get the minus sign in front of a B prime and I'd get a plus sign here for a prime B prime。

 or if I replace B by B prime， then I would have the minus sign in front of a prime B instead of in front of a prime B prime。

 or if I make both replacements，Enterchanging A and A prime and B with B prime。

 then that would put the minus sign in front of expectation value of A B。

So all of the inequalities are related by simple symmetries or relabeling of the names。

Of the settings to the CHSH inequality that we wrote down before so in a way there's no news here。

 the inequality that we found was the inequality that we already knew。

 but we we have learned something because now we know that the C。SH inequality and its cousins。

 which are simply related to it by symmetries， give us a complete characterization of the classical region。

 so if all of those CHSH inequalities are satisfied。

 then we know for sure we're in the classical region。

So because we have a complete set of bell inequalities here。

 it's not just that when we find a violation， we know that we're outside the classical region。

 we also know that if all of the be inequalities in that complete set are satisfied。

 then we are in the classical region。So that's good to know。Now， of course。

 one can also talk about the quantum region。What do I mean by the quantum region。 No。

 So now I'd like to know what are the。States。The probability functions， probability of outputs X， Y。

 given inputs A B that are possible in quantum theory， where Alice and Bob might。

Have shared entanglement， Let me get this move this a little bit so we unping the。Text there。

So how does that work while there's some density operator， let's call it row。AB。

 shared by Aliceison Bob could be an entangled state。

And Alice is going to make a measurement of her half of that entangled state。

 and Bob's going to do likewise。They have a list of possible measurements that they could choose from。

Altogether， M possible measurements labeled by a that Alice could pick。

 Each one of those measurements is a P O VM。That is， it's a。Expression for the identity。

 a resolution of the identity is a sum of non negative operators。

So Alice's measurement labeled A is a set of POVM elements labeled by a and X。

 and I guess I didn't write it down， but because it's a POVM。

 they have the property that for fixed A， if I sum over all the outcomes X， I get the identity。

And altogether there are M possible measurements she can make。

 each of which has V possible POBM elements， so for any value of her setting M。

 she does the appropriate measurement corresponding to that setting。

 she records her output and that determines x。Given A， and Bob is doing the same thing。

 He has some set of measurements altogether and measurements that he can choose from。

Each one of those is a POBM。And that's a resolution of the identity as a sum of non negative operators。

 they're altogether V operators。In the PLBM corresponding to the possible outcomes that Bob could get when he does his measurement。

And so the quantum model can always be written this way。

Is defined by some shared density operator shared by the two parties， All and P， some set of PO Bms。

 and the probability of getting the outcomes X and Y， given the settings A and B。

 is just the corresponding probability。Assigned to the measurement outcome in which Alice's outcome is X and Bobs。

Is why， so the elements of the POVM are all product operators。

Alice's POVM element tensored with Bob's POVM element。And that's what we mean by a quantum model。

 it's local in the sense that the things that are being measured are a tensor product of something that Alice measures and something that Bob measures。

 okay。But。What we learned。With great fanfare in the previous lecture。

Is that the quantum model includes。States。Conditional probability distributions that can't be realized in any classical model。

Because we saw that the CHSH inequality can be violated by quantum measurements performed by Alice and Bob on some shared quantum state。

It's also a true fact。That the quantum models contain as a subset all classical models。

It's always possible to realize the configurations。

Of a classical model as particular quantum measurements on particular quantum states and to construct within the quantum model convictx combinations of those so all of the points in the classical region can be reached by quantum models。

 so i'm using script Q to denote the set of all quantum models。And Sc C to denote the set of all。

Classical models。 and so C is contained in Q， but Q is strictly larger than C。And I tried to give。

A schematic。Illustration of。The situation in this drawing here on the upper left。

The classical models are a convex combination of exreal points。

 so I compressed it down so I could draw it。Just to to a plane， but in the schematic drawing the。

Vertices of。What I drew as a square are supposed to represent the classical configurations in which there's a deterministic outcome in which we have complete。

Knowledge of what。Output Alice is going to produce for each one of our inputs and the same thing for Bob。

And the be polytope or space of classical models is just the convexhull of those local configurations。

Quantum models contain those classical models， but also contain additional points。

 and the set of quantum models is not a polytope that corresponds to the observation that we made back when we talked about the B spheree description of a single qubit that the states of a qubit。

Actually， the space of states has an infinite number of exal points。 It's not just a polytope。

 not just a convictx combination of a finite number of possibilities。 Now there are also。

Bell inequalities， and I've indicated one of them here corresponding to one of the faces of the bell polytope。

A tight bell inequality if or know an extremeal bell inequality。

 what I called an extremeal element of the polar in my geometrical language。

 which hugs the bell polytope， which is lined up with one of its faces。

 theyre also bounds on how strong the quantum correlations can be like the cilcin inequality。

Which indicates some constraint on how far out the quantum models can extend in the space of states。

 and there are other classes of models that we might want to consider。

 One important one is the so called non signaling models。

What non signaling means as the name suggests， is that the correlations between Alice's outcome and Bobs for their various choices of setting do not allow any information to be communicated from Alice to Bob or from Bob to Alice。

 In other words， the probability distribution that Alice。Finds for her outcomes， for any setting。

Does't depend on what choice of setting Bob made， so to say that mathematically。The if I。

 for any choice of Alices， oops。For any choice of Alice's。Setting A and Bob's setting B。

 if I take the probability of Alice's outcome X and Bob's outcome Y and I sum over all of the possible outcomes。

 then I get a probability distribution for X， which depends only on a。

 which doesn't depend on B anymore， So all Alice can find out about if she doesn't communicate with Bob is this marginal probability distribution of her outcome X given her。

Input a， and if that doesn't depend on B， then Alice doesn't learn anything about Bob's measurement setting。

And likewise， because we don't want signaling to occur in either direction。

The sum over x over all of analysis outcomes of px Y given A B should be a probability distribution for。

Bob's outcome Y that depends only on Bob setting and doesn't have anything to do with Alice's setting。

Now， we should notice。That the quantum correlations are non signaling。

Let's look at our quantum expression for P of X Y given AB。

 it's because of the way we describe the measurements locally that each one of the POVM elements is a tensor product of one for Alice and one for Bob。

Suppose for fixed A and B。And X。I sum over all of the possible outcomes for Bob's POBM I'm summing over y well for each value B。

 it's a POBM and that means when I sum over y the E super B sub Y sum up to the identity。

So when I sum p of Xy over AB over y， the second factor in the tensor product just becomes the identity。

And so now I can describe the probability distribution of。

The outcome X for Alice as just the trace of her POVM element times the marginal density operator for Alice。

 because I just have the identity acting on Bob's system， I can trace Bob out。

 and this just becomes the trace of EXA row A that has nothing to do with Bob setting。And likewise。

 if I reverse the roles of Alice and Bob， there's no signaling in the other direction either。

 So quantum correlations are non signaling， but there are non signaling models。

 which can't be realized in the quantum models。 So the set of non signaling models。

 which obey this condition is actually larger than the set of quantum models。In fact。

 it is a polytope unlike the set of quantum models。Which includes all the quantum models。Inside。

The set of non seing correlations， as I said。Is larger than the set of quantum models。

 And the way to convince you of that is to give you an example。Of a model which is non signaling。

 but can't be realized in quantum theory。 What do we know about what can't be realized in quantum theory。

 Well， we know Cyilson's inequality for the C H S H game， right。

So remember Cyson's inequality expressed in the language of a cooperative game。

Says that in the CH SH game， there's no strategy in。

Quantum physics that allows us to win the game with a probability better than 0。853。

If we sum uniformly over all the possible inputs。In fact， though， there are non signaling models。

In which you can win the CHSH game with probability one for any input。Let me give you an example。

Okay， suppose that for inputs。To Alice and Bob，0，0，0，1 and 10 that the output is either0，0。

0 for Alice，0 for Bob or one for Alice1 for Bob， with those two possibilities both occurring with the same probability。

 each with probability one half， that means that for all of these settings， they win the CHSH game。

 because as you recall， if the and of A and B is 0 as it is in these three cases。

 then in order to win Alice and Bob have to produce outputs that are the same。

Either both zeros or both ones， and so both of these possibilities win。On the other hand。

 if the input is。A B equals 1，1， then the and is1。 that means in order to win the CHSH game。

Alice and Bob are supposed to output different values， either 01 or 10。

 so suppose in the case where the input is 11， they output equal probably either0 for Alice1 for Bob or one for Alice0 for Bob。

 then they win the CHSH game in that case as well for input a comma B equals1 comma 1。

So that's a model in which you can win the CHSH game with probability one for any input。

 we know that it's not a quantum model because the cilcin inequality told us that's not possible you can't win with probability better than 0。

853 when you average over all the inputs uniformly。On the other hand， this is a non signaling model。

Because no matter what the inputs are。Let's look on Alice side， she will output。For any input。

 either zero or one。With equal probability。 So it doesn't matter what Bob does。

 whether his input is0 or one for either input by Alice， either0 or one。

 she's just going to output a random bit。Probability one half of being zero。

 probability one half of being one that doesn't tell her anything about thought setting。

 that means it's a non signaling model， but it's not a quantum model because。

It violates the serial symptom。Okay。So let me just summarize a few facts about quantum models。

 you're probably getting tired of all this stuff。Well， I don't know， maybe you're not。

 but at any rate I'm not going to go into any more detail about this。

 but I already made the assertion that the quantum region contains the classical region as indicated in the diagram。

 anything。Any correlation that occurs in a classical model can be realized by some shared state。

Shared by Aliceison Bob and some suitable measurements。

The quantum region is contained in the non signaling region， I showed you that。

It's because of the nature of the measurements that it's a product of a measurement for Alice and a measurement for Bob。

The quantum region actually is convex， I guess that probably doesn't surprise you。

 it's a little tricky to show it， which I'm not going to do here。But as I said， it's not a polytope。

嗯。The non signaling region， on the other hand， is I guess I also remark。

Is a polytope also convex larger than the quantum region。Well， two other remarks I want to make。

Is that if the density operator shared by Alice and Bob in the quantum model is separable。

 if it's just some convex combination of product states， if is not， if it is not an entangled state。

Then the quantum model lies in the classical region。

Then they're not able to violate any bellinequality。

They need entanglement to do that without entanglement， no bellinequality violation。Furthermore。

 if the parties are choosing among measurements， if the different measurement settings correspond to measurements which are all commuting with one another。

Then there's no bell in equality violation。 If you want to have be inequality violation。

 then Alice has to be choosing。 And so does Bob measurements。Choosing among measurements。

 which are not mutually commuting like。We saw in our CH SH game example that we have to consider Alice and Bob making measurements of a qubit。

Along axes in the B sphere， which corresponded to non commuting measurements of theirqubit。

 So for bell andequality violation， we not only entanglement， shared by Alice and Bob。

We also need non commuting measurements。And。Well， I've described everything here for the case of two parties。

 Of course you could tell a similar story for any number of parties as long as it's two or more and I could。

Can characterize。All of the。deterterministic local configurations for end parties。

 just like I did for two， I could define a classical region and a quantum region and。

Make similar statements about the。Quantum region extending beyond the classical region。

The classical region being characterized by a set of bell andequalities。

 which correspond to the faces of the polytoe， to the exal points。Of the polar。

But the story can get pretty complicated if we go to many parties。And。Many settings and。

Many measurement outcomes， but even if it's just many parties。Lots of。

Local configurations keep track of high dimensional state space。Hard to visualize。

 not so easy to compute。 So we really don't have a nice analytic， close form。

Characterization of a complete set of bellinequalities。In。More complicated cases。

 we only know that for a few relatively simple cases。So that's my story about Bell inequalities。

 I hope it was。Enlightening， I know it brought in concepts。

Which maybe I didn't explain particularly well， but I was just trying to get you to appreciate the music of the geometry of bellinequalities。

How on the one hand， we can characterize them in terms of。The extremeal points。As a polytopque。

 on the other hand， characterize them in terms of。Extreme mole hyperplanes， the set of faces。

That that characterization in terms of faces， once you know it is a very convenient way to test whether a state which you may have encountered experimentally。

Can be explained by a classical model or not。Okay， so what I'd like to start doing next time is talking about some of the things we can do with quantum entanglement。

Like quantum teleportation。But I think that'll do it for now。So I will see all。Next time。

 take care of yourselves， be well， See you soon。

![](img/7dd544283990f2b328a2ca415cc6c62e_3.png)