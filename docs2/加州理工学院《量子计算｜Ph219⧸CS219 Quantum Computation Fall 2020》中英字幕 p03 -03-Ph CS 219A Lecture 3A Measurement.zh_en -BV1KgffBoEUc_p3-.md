# 加州理工学院《量子计算｜Ph219⧸CS219 Quantum Computation Fall 2020》中英字幕 p03 -03-Ph CS 219A Lecture 3A Measurement.zh_en -BV1KgffBoEUc_p3-

![](img/47ceedcb38abd8a73ea66532e436b4b7_0.png)

Hi everybody， welcomecom back to the second week of Phy Comp Science 219 a quantum computing。

 I hope you're all well。 I hope you're all getting into the swing as the academic year。Perhapsps up。

In this， the third lecture of the course， we're going to continue with our discussion of density operators and also discuss a generalized notion of measurement。

 so let's get to that now。So this is really the second of a sequence of lectures in which we will be developing the theory of open quantum systems and you'll remember that we say a system is open if it can exchange energy and information with its environment where we're not monitoring the environment last time we talked about how to discuss states of an open system those are described by density operators that is non-ne permissionmeian operators with trace one。

And we also discussed the idea of a schmidt decomposition of a bipartid pure state。

Now today I want to talk about measurements that are more general than the orthogonal measurements that were specified when we formulated the axioms for closed systems。

These are measurements that can be realized when a system interacts with an auxiliary system。

 and then an orthogonal measurement is performed on that auxiliary system。

 and the result of that is something more general than applying an orthogonal measurement to the system itself。

But before we get into that， we're going to continue the discussion of density operators for a little while and get to some additional concepts that we didn't get a chance to cover in the previous lecture。

 so we'll be continuing with material in chapter two of our notes and then onward to the discussion of measurement in chapter 3。

 I'd also like to point out that the first homework of the course has now been posted。

 there's a link to it on the course website and the homework is going to be due a week from Friday on October 16 and we will have instructions on Canvas and Piazza about the process for submitting your homework and having it returned to you。

So let's remember what we said last time about the idea of a density operator。

 we can imagine splitting the universe into two parts。A system A。Under Alice's control。

And we're interested in what kind of observations Alice can make when she looks at system A。

But there's actually a joint pure state。For the closed system consisting of Alice and her environment。

 which we're imagining is under the control of another party， Bob。

So there is some bipartid pure state which I can expand in terms of an orthoormal basis for alysis system and boOB system。

 but if we want to consider any measurement that can be done on alysis system alone for the purpose of assigning probabilities to the measurement outcomes。

 we don't need the full bipartid state， all we need is the density operator for alysis system。

 which is obtained by performing a partial trace over boB system。

 and in terms of an ortho andormal basis for alysis system that can then be expressed as I'm showing here in the expression for RA。

 given that the joint system is this bipartid pure state expanded in terms of complex coefficients and a orthoormal basis。

 and we observe that a density operator obtained in this way has three fundamental properties。

 that it is first of all a hermeian operator。It is also a non negative operator。

 hermeian with real eigenvalues， which are non negative real numbers。

And the density operator has trace one that corresponds to the feature that if we perform any measurement on A' system and assign probabilities to the outcomes。

 those probabilities have to sum up to one because some outcome occurs each time a measurement is performed。

We also noted that because it's a Hermeian operator。

 there is a basis in which the density operator is diagonal。And the eigenvalues。

Of the density operator， the coefficients of projectors onto those orthonormal basis states of the density operator can be interpreted as probabilities。

 they are non-neative real numbers such that the sum of all of the PIs is equal to one and in fact we can give a nice interpretation to the density operator we can imagine that someone has prepared a state of analysislysis system in the following way that the state is prepared in one of those orthonormal basis states in the basis that diagonalizes the density operator and that Alice consults some source of random numbers and by doing so she samples from a probability distribution and with probability p sub I prepares the orthoormal basis state I and although that might not really be how the state was prepared。

for any practical purpose of interest to Alice， for any measurement that she performs。

 she can tell the difference between making a measurement on a state prepared in that way and making a measurement on Alice's half of this bipartid pure state。

 which has the specified density operator。Another thing we talked about was a particular basis in which a bipartid pure state of systems A and B has a special form。

 this is called the Schmidt basis and that special form of the bipartid。

Pure state is called the Schmidt decomposition what we do is we use the basis in which Alice's density operator is diagonal to express the state in terms of a basis for Alicelysis system and also the basis in which Bob's density operator is diagonal obtained by doing the partial trace over AliceIS。

And then the bipartid pureate has this simple form， it's a sum over a single index。

 the square root of a probability， an eigenvalue to the density operator。

Orththeormal state I for Alice and what I call i prime one of the orthonormal basis states for Bob so the basis elements are paired up in this way in the bipartid state once we've chosen that schmidt basis or the basis in which the density operator is diagonal for both systems and one way of thinking about how we arrive at the schmidt form is if we look back at the a bipartid pure state in its general form here in terms of。

Some general orthonormal basis for alysis system and bombs this。

Matrix AI mu in general a rectangular matrix because Alices and bo systems might have different dimensions can like any rectangular matrix be expressed in terms of a singular value decomposition if we have the freedom to make a unitary change of basis for the first index and another independent unitary change of basis for the second index we can put that matrix into a diagonal form with non-neative coefficients。

 that's the singular value decomposition of the matrix and by choosing those basiss that put the a matrix in that。

Singular value form， we can perform the schmidt decomposition or put that bipartid pure state into the Schchmidt form。

And we can see from the Schmid form， one consequence。

 which is that when we do the partial trace over Bob system， we get probabilities piece of bi。

 those are the eigenvalues of Alice's density operator。

 but if we perform the partial trace over Alice's system to get Bob's density operator。

 we get a density operator which has the same。Eigenvalues。

 so the nonzero eigenvalues of Alice's density operator and bos。

 if they share a bipartid pure state are always the same because the dimensions of the two systems might be different。

 the number of zero eigenvalues might be different for Alice's system and bos。

 but the nonzero eigenvalues are guaranteed to be the same。

Now there's a kind of geometrical property of density operators。Which is useful to know。

We can think of the density operators as living in a linear space。

 we can imagine taking linear combinations of density operators and the space of possible density operators or density matrices of some specified finite dimension is a convex space。

what that means is that if I have two density operators， let's say row1 and row2。

 and then I consider taking the sum for some real number between0 and1 lambda lambda row1 plus one minus lambda row2 that's called that linear combination row of lambda that also is a density operator。

 remember by a density operator， we mean an operator， which is hermeian。

And has non-neg eigenvalues and has unit trace Well it's actually obvious that if row 1 and row2 are both hermeian。

 then this linear combination is also hermeian because lambda and 1 minus lambda are real numbers equal to their complex conjugates。

 it's also obvious that the trace will be one per rh of lambda。

 if the trace of row 1 is one and the trace of row2 is one because the trace of rh of lambda is just lambda times the trace of row 1 plus1 minus lambda times the trace of row2。

Now we should also ask whether row of lambda is a non-negative operator， I said positive。

 when I say positive， sometimes I really mean non negativeative。

 what I mean is it doesn't have any negative eigenvalues， or in other words。

 if I take the expectation value， the diagonal matrix element of rh of lambda in any pure state。

 then the result has to be a non-ne real number。Well what we can see is that if we substitute in the expression for row of lambda。

In this matrix element between psi on the right and psi on the left。

 the result will be lambda times the expectation value of rh1 plus1 minus lambda times the expectation value over row2 and because row1 is non negative and row2 is non negative and because lambda and one minus lambda are non negative。

 this is a sum of non negativegative numbers and therefore has to be greater than equal to zero。

 so rh of lambda is indeed a density operator。Now，Rolandda has a nice interpretation。

Because we can imagine that there's some party， Charlie， who is preparing a state of Alice's system。

 and he does it in the following way， he's going to prepare for Alice either the state row1。

 the state described by density operator row1 or the state row2。

 and he's going to do so with assign probabilities。

 numbers lambda and 1 minus lambda to that sum to1， so he flips some coins。

 he consults some randomness， he samples from a distribution， and with probability lambda。

 he prepares row1， or with probability1 minus lambda he prepares row2。

And the state prepare that way is certainly a possible physical state of the system。

 There's nothing wrong with Charlie consulting some randomness to decide whether to prepare row 1 or row 2。

 But there isn't any way that Alice can tell the difference between a state described by the density operator row of lambda or a state which was either prepared as row 1 with probability lambda or row 2 with probability 1 minus lambda for any observable that Alice might want to measure。

We can consider the expectation value。I both the expectation value with respect to that distribution that Charlie consults and with respect to the expectation value in Hilbert space of the density operator。

 whatever it be， row1 or row2， and then with probability lambmbda， Charlie has prepared row1。

 and then the corresponding conditional probability or conditional expectation value of M would be the trace of row 1 m。

With probability one minus lambda Charlie has prepared row2 and conditioned on that preparation。

 the expectation value of M would be the trace of row 2 m so altogether the expectation value of M is just the trace of rh of lambda M so this preparation that Charlie carried out by consulting a source of randomness is really just a way of preparing the state which we called rh of lambmbda。

So geometrically， we can think of。The space of possible density operators in the space of all possible D by D matrices。

 if we're considering a D dimensional system。As a convex space in the following sense。

 I consider any allowed density operator row1 and any allowed density operator row 2。

 and then I can consider a straight line connecting those two points undefined as I defined row of lambda here。

 and every point along that line with the two endpoints。

 row1 and row2 is a possible density operator of the system， that's a property of a convex space。Now。

 if you're given a mixed state。There are actually lots of possible ways to prepare that state by sampling from an ensemble。

 and we can kind of see that from this geometrical picture if we pick out some point。

In the interior of the set of all possible density operators in our space of D by D matrices。

Then consider the point that I'm pointing to here with my red laser。That can be expressed。

 That is it contained on many different line segments that go through that point。

 And for each one of those segments， I can imagine preparing this state。

As a convex combination of say these two states so if this is row1 and row two by choosing the appropriate weights I can prepare a state which lies anywhere along that line segment connecting the two blue dots and with the appropriate choice of lambda I hit this point here but I could also choose two other points in the set of possible density operators and draw a segment connecting them that goes through that same point and so that's a different preparation as an ensemble of two different density operators with appropriately assigned probabilities that gives me exactly the same density operator from the geometrical picture we can see there are lots of preparations of a particular state as convex combinations of two or more。

Density operators。But there's an exception。The pure states don't have that property。

 the pure states are what we call extremeal， meaning a pure state density operator cannot be obtained as a convex combination of two other density operators well let's see why that's true。

So suppose I have some pure state here， it's just the projection onto some state vector psi。

 and suppose I could write it as a convex combination of sum row1 and sum row2。

Now for any vector in Hilbert space， psi。Let me consider any vector I please。

 which is orthogonal to psi。I call itsi perk。 It has the property that the inner product of Pi perk with Psi is equal to0。

 So now let's consider the matrix element of row， which in this case is this pure state。

Between side perp on the left and side perp on the right。

 well obviously that's zero because I just get the inner product squared of side perp plussi and because side perp and psi orthothgonal that's zero。

Now， if row can actually be written in this as this convex combination。

 then zero will also be equal to lambda times the。Expectation value of row1 in the state side perp plus1 minus lambda times the expectation value of row2 in the state side perp。

But that means that zero is a linear combination of R zero。And if lambda is not equal to zero or1。

 that means that for both row1 and row 2， the expectation value inside perp of row 1 and the expectation value inside perp of row2 is equal to zero。

 but remember I could have chosen psi perp to be any vector which is orthogonal to psi。

 and the only way that row1 or row2 could have the property that the expectation value for any such s perp is equal to zero would be for row1 or row 2 to be the pure statesi to be the projection on two psi。

Okay， so that means that our attempt to construct the pure state as a convex combination of two other density operators has failed。

Okay。So that's why we call it an extremeal state， that's what's pure amount of pure state。

 it can't be obtained as a convicx combination of two other density operators。

 it can' be obtained by consulting some random source。

 some probability distribution and preparing either row1 or row two。

Now we talked before about the pure states of a qubit。

 but now I'd like to talk about mixed states of a qubit。

 what is the most possible density operator for a qubit for a two dimensional quantum system。

 a quantum system who's Hilbert space is two dimensional well。

A density operator in this case is a two by two matrix， which is hermeian。And non negative。

And has trace one so here I've written down the most general form for a two by two matrix which has trace one and is hermeian that's a space of matrices which is three dimensional it's described by three real parameters the off diagonal elements whoops。

 the off diagonal elements。Of this matrix are complex conjugates of one another because Ro is orthogonal and the。

On diagonal elements， the 00 and11 element have to have a sum of1 because this matrix has trace1。

 so it was convenient to pull out a factor of1 half and to write that in terms of the real parameters。

 P3， P1 and P2。So now this is a two by two matrix which is hermeian and has unit trace。

 but we have to check that it's not negative， that it doesn't have any negative eigenvalue。Well。

 since it's just two by two， and because its determinant is the product of its two eigenvalues。

 being non-ne means having a non-neative determinant because it has trace one。

 if one of the eigenvalues is negative the other one has to be positive and the product of the two would be negative。

Now it's easy to evaluate the determinant of a two by2 matrix and in this case we got a factor of1 half squared that I can factor out and the product of the 00 and 11 components of this matrix is a1 minus3 squared and then minus the product of the01 and10 components of the matrix that means minus p1 squared minus p2 squared so I can write the determinant of rh is one minus the length squared of a vector whose components in a three dimensionmensional real space are p1 p2 and p3。

 and for a non-negative density operator that's got to be non-negative which means that the length of this vector has to be less than or equal to1 if it's less than one then the determinant is non-zero and that means that there are two non-vanishing real positive eigenvalues and if it's。

equal to one then the determinant is zero and that's the case of a pure state where one of the eigenvalues is one and the other eigenvalue is zero so if we want to think about density operators of a qubit in geometrical terms。

 we can envision a ball in a three dimensional real space。Where the coordinates in that space are P1。

 P2 and P3， we can draw a sphere。Where the radius is one that the length of the vector p is equal to1 and those are the pure states。

 we talked about those before， we talked about the pure states of a qubit being in correspondence to points on a two dimensional sphere。

 but in the case of mixed states， we can imagine filling in that sphere filling in its interior and all the points in the interior are possible。

Density operators for our two dimensional system。So there a space of states of density operators for a qubit。

Is called the block sphere block was。Person， Felix Bch that it's named after。

 and it's really not such a great idea to call it a spear because it's really a ball and includes the points which are in the interior。

OfOf the sphere， but people often speak to the black sphere with either pure states。

 which really are on a sphere。Or mix states which are in the interior of the ball in mind。Well。

 as I said， the boundary of this block ball really is a sphere。😊。

That's when the determinant is equal to zero， that's when the state is pure and that's what we already discussed in the previous lecture we talked about the possible pure states of the qubit being in one to one correspondence with points on a two dimensional sphere。

We can recover what we said then in the following way， so the density operator for a pure state。

 that's the case in which the length of the vector p is equal to1 in other words it's a unit vector。

 so that becomes one half times identity plus n hat a unit vector sigma and property you can easily check and I think we talked about last time is you take n hat do sigma。

For any unit vector and hat， and remember by vector Sigma， I mean the poly operators， Sigma1。

 Sigma 2 and Sigma 3。And no matter what N hat is， if you square that operator you got the identity。

 so in other words， it's eigenvalues are plus one or minus one。

 so that corresponds to if you measure N hat dot sigma for a。For a qubit， you will get outcomes。

 which are either plus1 or -1。 Now， since N had dot sigma squared is equal to1。

 we can see the following thing that if I multiply this density operator。

Row of n hat on the left by n hat dot sigma well then I get n hat do sigma plus it's square here。

 which is the identity that in other words I just get row back again and likewise if I multiply row of n hat by n hat dot sigma on the right I just get row back again so in other words。

What that means is that Ro of eventhead is just the。

Pure state of a qubit that we talked about last time I labeled Nha using polar angles theta and phi and remember the pure states could be written as state vectors of the form that I called psi of theta and phi。

 the density operator is just the projection onto that state vector now another thing that's good to know about these poly operatorsators is that if I consider I and J to vary over1。

2 and3， the three poly operatorsators。嗯。Sigma one， Sigma two sigma  three。Actually。

 let me come back for a second because I didn't say this clearly enough if I go back to my form row of P hatAT。

 you can see that what I've written here after I factor out the one half is p3 times the diagonal matrix with eigenvalues。

1 and minus1。 And that's just p3 times sigma 3。 And then remember that sigma 1 had entries1 in the upper right and lower left。

 So here I also have p1 times sigma 1 and that sigma 2 had entries minus I and I off the diagonal。

 So this contribution is just P2 times sigma 2。 And so that's why I was able to write this as identity。

 that's the diagonal part a1 in the upper left and in the lower right plus vector P dotted with。

Sigma that is p1 Sigma 1 plus P2 sigma 2 plus p3， sigma3。Now。

 another nice thing to know about these sigma matrices is that。

If I take the trace of sigma i sigma J where I and J run over1，2， and 3。

 that trace vanishes unless I is equal to J， if I is equal to J。

 then the product is the identity which has trace2。

 so I can write the trace of sigma i sigma J as2 delta J， the Ch or delta。Now。

 if I'm interested in the density operator described by P， that is this row of P， in that state。

 if I'm interested in the expectation value of N had do sigma， the expectation value。

 the average value of N do sigma， if I measured many times。

That is the trace of the density operator times that observable so let's just expand that out I can write the n hat dot sigma as the sum over I N sigma I I can write to the P dot sigma as the sum over J Pj sigma J when I take the trace only the terms with I equals J s I get a two here in front of the delta j which cancels the1 hat in the normalization of the density operator so what we're left at with is just the sum of N pi it's just the dot product of that unit vector n and the vector P which。

We used to label the density operator。So that's the expectation value of the spin along the N axis of。

In the state described by the vector P， we call P the polarization of the qubit。

 it tells me what direction。To。嗯。Choose to measure in order to maximize maximize that expectation value and when the polarization。

Is is actually。A vector which has unit length， those are the pure state so that if I choose the right access。

 I'll have an expectation value one， I'll always get the outcomes spin one along that axis。

 but for the mixed states the expectation value is diminished。And。

We call that the polarization since it characterizes the expectation value。

 if you think of it as a spin， polarized or pointing in some direction。Now， as I've said。

Every mixed state of a quid。Can be expressed as a convictx combination of two pure states。

And fact can be expressed that way in many ways well actually maybe I haven't said that yet so what's the idea well here we're talking about a qubit all the possible states live in the ball I can pick any point in the interior of the ball。

And then if I want to。Consider any chor of the ball。

 any straight line that connects together to points on。The boundary of the ball。

If that line goes through this point in the interior。

 then that means that this density operator can be expressed as a convex combination of these two pure states which live on the boundary。

Now， with the exception of the maximally mixed state， that's when the polarization is equal to zero。

 the density operator is just one half the identity and that's the point at the origin of the sphere。

If I want to express the density operators a convex combination of two mutually orthogonal pure states。

 there's a unique way of doing that because the pure states which are mutually orthogonal。

 are the antiptal points on the sphere， that is if I consider a line which goes through the center of the sphere。

 a diameter of the sphere， then the two points on the boundary。

That that line intersects are pure states that are mutually orthogonal。

 Those correspond to if we were to measure the spin。Along the axis picked out by that diameter。

 the two endpoints are the states which always are spin up or always are spin down when we measure along those direction。

 along that direction， and those are mutually orthogonal and we discussed that when we described the pure states of a qubit in the previous lecture。

But there's nothing wrong with expressing this point in the interior as a convex combination of two states which are not mutually orthogonal。

 in other words I can consider any chord and if it goes through this point。

 the density operator I'm trying to describe then where that line meets the boundary。

 those are pure states and the appropriate convex combination with the right weight of the two endpoint。

 I'll hit this point， in other words I'll have expressed that density operator as a convex combination of those two pure states which are not mutually orthogonal。

Now。Another thing to note is that in the case of a qubit。

 in the case of a two dimensional Hilbert space。Every state on the boundary of the space of density operators is a pure state。

The space of density operators is the ball with unit radius in three dimensional space。

 the pure states are。The sphere with unit radius， the boundary of the ball and every point on that sphere is a pure state。

In higher dimensions， the situation is different。In that case。

 we can have a density operator which is on the boundary of the space of possible density operators。

 but is not a pure state。I'll show you what I mean by illustrating with the case of a three dimensionmenal Hilbert space。

 so consider some density operator for a system with a three dimensionmensal Hilbert space expressed in terms of the projections onto the eigenvectors of the density operator。

 let's call those eigenvectors zero1 and two， then there's some non-neative real number。

 projection onto zero plus non-negative real number projection onto one plus non-neative real number projection onto the state two。

That's what the density operator looks like in its diagonal basis now if any one of those probabilities p0 p1 p2 which sum up to one。

 if any one of those is0 that is on the boundary of the space of density operators which are non negative permeian operators。

 in other words， if let's say p0 is equal to zero then there are。Marices。

 three by three matrices which are arbitrarily close by。

 which are not density operators because they have eigenvalues which are just a little bit less than zero。

 but if I set p0 equal to zero， so I'm right on the boundary of the space of state。

 what I have is not in general a pure state rather it's a convicx combination of the state 1 and the state2。

 unless either p1 or p2 is also zero。Okay， so the boundary is not the same as the set of pure states。

In dimension three or greater。Now， this idea of extremeal points of probability distributions。

 we can also discuss classically。And if I have a probability distribution in three dimensions。

 that is if I want to consider probabilities assigned to three possible outcomes。

 let's called them P0 and P1 and P2， like I did here。

Then have I consider the space of all such probability distributions？In three dimensions。

 there are three possible extreal points。We can visualize the geometry of that space of probability distributions。

 as I've shown here with this triangle， here I'm considering along the horizontal axis。

 the value of the probability of outcome zero。And along the vertical axis。

 the probability of the outcome one。If both p0 and p1 are equal to zero。

 then that means p2 is equal to1， so that is one of the extremeal points where one of the outcomes in that case。

 the outcome two has probability1 okay。Up here when p1 is equal to1 well then of course p2 and p0 have to be equal to0。

 so that's another extremeal point where the outcome one occurs with probability one and then there's a third extremeal point when。

Here where p0 is equal to1， which means both P1 and p2 have to be equal to zero。

Now every other probability distribution。😊，Governing those three possible outcomes， labeled zero。

1 and 2。Can be expressed as a convex combination of those three extreme of points of this vertex of the triangle。

 this one and this one， all those possible convex combinations are all the points in the interior of the triangle colored here in gray。

So likewise， if I were considering D dimensions， the space of all possible probability distributions could be expressed as a convex combination of Dexal distributions。

 and in each one of the extremeal distributions， one of the outcomes occurs with probability one。

Notice that in the quantum case in the case of quantum states quantum density operators。

 the geometry is different and in fact already in two dimensions。

 we see that although the Hilbert space is just two dimensional and the density operators have three real parameters。

The exal points are all the pure states， there are an infinite number of them。

 every point on the unit sphere is an exreal point。嗯。嗯。Now。As I've said。

If I want to express a density operator which is mixed as a convicx combination。

Of possible peer states。For any mixate， there are many ways of doing that。 remember。

 we visualize that in the case of the qubit by noticing that this point in the boundary of the sphere could be expressed as either a convex combination of these two red points or a convex combination of these two。

 and there are many other possibilities as well an infinite number。Let's be more general。

 let's suppose we have a Hilbert space since some unspecified finite dimension。

let's say D dimensions。And I can imagine expressing a density operator as a convex combination of pure states。

 now the number of pure states in that convex combination can be any number。

 even if the Hilbert space dimension is three say there's nothing wrong with considering a convex combination of 18 possible density operator a possible pure states to get a density operator。

I could consult some probability distribution for 18 outcomes。

 I sample from it and then prepare one of those 18 pure states to obtain the density operator。

So here I haven't specified what I'm summing A over。

 but it's being summed over some finite number of values and the density operator was obtained by with probability PA preparing a pure state。

 which I called PA。So given a set of pure states and a corresponding probability distribution。

 that specifies an ensemble representation of a density operator。

But that same density operator might instead be expressed as a convex combination of some other set of pure states now these phias and these s mus don't have to be mutually orthogonal as we saw here。

 I could consider this chor in the case of thephere which is not connecting to antipental points and so that describes a density operator in terms of an ensemble of states which are not mutually orthogonal。

 so I don't want to assume here that the states labeledsi mu or the state labeled phia are necessarily orthogonal to one another。

 but what I would like to understand is what can we say about the relationship between the state s mu and the probability distribution Q mu and the state's phia and the probability distribution PA。

 if both our ensemble representations of the same density operator。

Now if I'm given a density operator， there's something I can always do if I want to。

 and that is I can purify the density operator this is a density operator just for Alysis system a。

But let's suppose I imagine that although I only have access to system A。

 that there is some system B and that the density operator for system A was actually obtained by taking a partial trace over that system B。

Well I can always construct such a pure state， in fact。

 if I want this density operator in which Phi A occurs with probability PA。

 I can just consider this pure state of AB， I let the alpha A's be some ortho theormal basis for system B。

 so I'm going to have to choose the dimension of system B to be large enough to have a dimension which is at least as large as the number of states phi A and the ensemble that I want to sample from。

But if I introduce an orthoormal basis and assign a different element of that basis for system B。

Teach one of the PhiAs， I can construct this pure state for A B， and when I trace out system B。

I'll just recover this density operator I can do just evaluate the trace using this alpha a basis so that's easy to see。

Well， likewise， for this other ensemble。In which I'm preparing the pure state size sum mu with probability Q sub mu。

 I can introduce some other。Ororth a normal basis for system B。And construct a pure state for AB。

 not necessarily the same one as PhiA。I'm going to call this one52。

And by pairing up orthoormal basis states for Bob system be subu with the state s mu that I want to。

Use in my convex combination to construct row if I now trace out system B。

 I will get this representation for the density operator so if these these are。Indeed。

Two different ways of realizing the same density operator， there's some kind of relationship。

Between Phi1 and P phi2 that we'd like to understand。

But one way of thinking about this is that in the state51 we can imagine that Bob performs a measurement。

 he doesn't really have to do this， we can just trace him out。

 but suppose we imagine that Bob performs a measurement of system B。

In the alpha basis and he does so when the bipartid state is the state Phi 1。

 Well then he's going to get the outcome alpha a with probability P and when he gets the outcome alpha a。

 he will have prepared Phi A。 So that's just a way of realizing this ensemble representation of the density operator。

 we can imagine we have this bipartid pure state Phi 1 and Bob measures in the alpha basis and then that means he's preparing Phi a with probability PA。

And on the other hand， if the。Bibpartid pure state for A and B were phi2。

Now Bob can measure in the beta basis and he'll get the outcome beta mu with probability Q mu when he gets the outcome beta mu he will have preparedsi mu for Alice's system so that's a way of realizing the ensemble representation in terms of the pure statesi mu occurring with probability Q mu another way of representing the same density operator row A so now we'd like to ask how are these two states phi1 and phi2 related。

 and what I claim is that it's possible for Bob to turn the first state phi 1。

 into the second state phi2 just by performing a unitary transformation on his system on system B。

Without ever touching system A。So actually what that means is。That there's a single purification。

Of A， a pure state of system A B， such that Bob can measure in either one of two bases。

And in one case， he'll be realizing the ensemble Phi A with probability PA。

 and when he does the other measurement， he will be realizing the second ensemble preparingsi mu with probability Q mu。

Because if I can get one state from the other just by performing a unitary for Bob。

 all he has to do is perform that unitary first and then measure and it'll be the same thing as the description I gave here of measuring in the databases in the state。

51 so this statement that there's a single purification such that Bob can realize either of these ensemble representations by doing two alternative orthogonal measurements just on system B。

 this is called the Houston Jozo Woods theorem or sometimes just the purification theorem。

And the way to see it's true。Is to make use of the smidt decomposition so we have these two states remember and we've been promised that if we trace out system B。

 we get the same density operator row A if the shared state is phi 1 or if the shared state is phi 2 now both phi 1 and phi2。

Can be put in Schchmidt form， I can choose。Or theormal bases for systems A and B。

 such that Phi1 is in the s Schmidt form， so it can be written as some。

Other probability distribution given by the。Um。The eigenvalues are the density operator row A。

Lambda K， of course in the Schchmidt decomposition we have the square root of lambda K rather than lambda K itself that's what will give us a normalized state phi 1 and then there's some ortho the normal basis for alysis system I've called the elements of that basis K and then there's some corresponding or the normal basis in the Schchmidt decomposition for boB system and I'm calling those a basis elements K1 prime the 1 in reference to the fact that this is the state phi1 and I can do the same for phi 2。

Now the lamb decays， remember， are just the eigenvalues of the density operator row away so those are going。

micro风啊。Hm。Is it working， Yes， it's working fine。Let's get rid of that and assume everything's good。

Okay， we're still recording。Remember that in the Schchmidt form。

 this basis for alysis system is just the basis in which the density operator is diagonal。

 so that's the same basis for Phi1 and Phi2 because they both have the same marginal density operator when we trace out B system。

So in order to get phi 1 from phi 2。All I have to do is rotate Bob's basis elements I to I don't have to touch Alices。

 I just have to rotate the K1 prime basis to the K2 prime basis。

 there's always some unitary transformation that does that that rotates unit one unitary basis to the other。

So Phi1 can be written as identity analysislysis system。

 we don't touch Alicelysis system tensored with some unittarian on Bob system acting on by two。Okay。

 and when we apply those unitaries to。Bas that we use to express phi2 here we just get some other basis and I guess I decided to call that the gamma basis for systems B so now look at what we have here we have a state phi1 which can be expressed in two ways it's the same state expressed in two ways and in the first way if Bob measures in the alpha basis he'll realize the first ensemble phi a with probability PA that's the alpha basis and in the other basis the gamma basis if Bob does an orthogonal measurement in that basis he'll be preparing si mu with probability Q mu。

Okay。In fact， I could always take this gamma basis and I could reexpress it in terms of the alpha basis by performing some unitary change of basis。

I can take。Take this expression。which is just a way of writing P phi1 and then use the expansion of the gamma muse in terms of the alpha A's。

 and that's some other unitary operator， and I can think of it as a matrix with matrix elementss VA mu。

So I can write。Phi1 either this way。Where if we measure in the alpha basis。

 we'll prepare the state PhiA with probability PA。But here I've expressed it in terms of the alpha basis just by including the unitary that rotates the gamma basis to the alpha basis and including the matrix elements of the VA muse。

And so we here we have two different expansions in terms of Bob's alpha basis and they have to agree because there are two ways of expressing the same state and we can see that what that means for each value of a square root of。

PA times。State vector phiA has to be the same thing as the sum of square root of Q mu。

 state vector si mu unitary matrix element V mu。So if we have two different ensemble representations of the same density operator。

 they must be related in this way for some unitary matrix V。Now。

 when we do the sum over a and the sum over mu。嗯。Though sums might have。You know。

 a different number of terms because the preparation in the phi basis and the preparation in the pi basis might have had。

A different number of possible states but that's okay we just choose the dimension a bo system to be sufficiently large as to accommodate the larger number of alternatives。

 whichever it is between the five basiss and the psi basis and then these are the matrix elements of。

A unitary where。Well， I don't have to worry about others which because there are things that occur with zero probability。

 but there's going to be some unitary B， which is a square matrix whose dimension is determined by whether the number of values of mu or the number of values of a is larger。

 such that the two ensembles are related this way and that's another way in which the HJW theorem is sometimes stated。

Okay。Okay， so let's move on to measurements。 we've been talking about density operators。

 but now I want to look at measurement as。Something more general than is encompassed by our measurement axiom for a closed system。

 so you can think of this as a kind of measurement in an open system。

 but let me motivate it in a somewhat different way。

Usually when we do a measurement on a quantum system in the laboratory the quantum system is some little itty bitty system it doesn't have to be。

 but it could be an atom or it could be the spin of an electron or something like that and it's hard to see that directly so if we want to read out the outcome of a measurement on that what do we usually do we find some way of coupling the system that we want to measure like the spin of the electron to some other system that's easier for us to read out some kind of meter or apparatus which we can look at。

 we can think of it as having a dial where the dial points to one of a set of possible numbers and well we can take it for granted that when we look at a dial it's easy to see whether it's pointing to one two or three and so on that's a lot easier than looking directly at the spin of the electron。

So we can think of the measurement process as a two step process。

 there's some quantum system we want to measure it。

So you could think of this as Alice and Bob again if you want to。

 and in fact I will go back to that notation in a moment。

 but for now I'm calling it S the system that we want to measure in a the apparatus。

 which is the thing that's easy for us to look at， never mind exactly how we look at it we have some way of looking at this meter and seeing what it reads so to do the measurement。

 first of all we need S&A to interact with one another we can start out in a state in which SNA are completely uncorrelated in a product state of a state for S and a state for a。

 but then we turn on some interaction between SNA and a unitary transformation occurs which xs collectively on SNA and after that unitary transformation is complete then we measure the apparatus。

And when we do so， we will have prepared some state of the system and we'll get some probability distribution for the outcomes of the measurement of the apparatus。

 and we can think of those as the probability of the outcomes for the measurement of the system and the post measurement state of the system is the state after our measurement is complete。

So let's suppose。That what we're interested in doing is performing an orthogonal measurement to the system。

But we don't know how to do that directly， however。

 we do know how to do orthogonal measurements for the apparatus。

So let's suppose that the different outcomes for the measurement of the system that we want to describe。

Are labeled by orthogonal projectors， I've denoted them EA。

Remember that these what it means for them to be orthogonal。

 they're hermeian operators and they have the property that when a is not equal to B EA EB is equal to zero on the other hand EA squared is equal to EA EA is just the projection onto some subspace and we'll also assume completeness that。

When we sum up all the possible projectors， we get the identity on the Hilbert space of the system。

 so that's what we'd like to measure。So how should we choose our unitary so that we can do our desired measurement on the system by measuring the apparatus。

 well we'll suppose that there's some corresponding orthoormal basis for the apparatus and that somehow we know how to perform the orthogonal measurement on the apparatus and we want to leverage that ability to perform the orthogonal measurement on the system。

So I'll write the unitary this way。And you see， we're summing over a。

 which labels the different alternatives for our measurement of the system。

And corresponding in the sum to the projection EA acting on the system， there will be a shift。

In the basis for the apparatus， though the elements of the apparatus are labeled by a。嗯。Oh。

 wait a minute。H。系 think佢。Yeah。Yeah。And I think maybe this isn't right， hold on。哦。

Bear with me here for a second。

![](img/47ceedcb38abd8a73ea66532e436b4b7_2.png)

嗯。