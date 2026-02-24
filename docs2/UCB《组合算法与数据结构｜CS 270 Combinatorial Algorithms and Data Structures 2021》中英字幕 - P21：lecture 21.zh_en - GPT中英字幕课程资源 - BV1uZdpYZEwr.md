# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P21：lecture 21.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/e46a987a7fb34cd32ed9a6611dbe282c_0.png)

Okay， so。So just to refresh a memory， last class what we did was we defined the sum of squaress DP hierarchy。

 it's a degreeD sum of squares DP hierarchy。Compututes the moment of a。

Distribution or pseudo moments of a distribution over solutions to a polymial system。Okay。

 and so basically given any polynomial system。The IFX greater equal to0。For I equal to1 through M。

The degree D。SOS S SDDP solution。Essentially gives you。呃。Sudo moments。Of a distribution。Or solutions。

To the polynomial system。So I call it pseudomo because you never actually know if there's an actual distribution for which these are moments。

 you just get a bunch of numbers which are supposedly the moments of a distribution and most likely there are not but you still want to work with them it's like the fractional solution of a vertex cover LP there is no there might be no real distribution of vertex cover solutions with that as your fractional。

Values， but it's just。I is what you get。Okay， and。And so we didn't figure out how to sort of analyze this or prove statements about the pseudo movement。

 right？What if it's how do we prove that？These numbers that we get are not pure garbage from it。

 or how do you extract solutions to original problem from these pseudomoments？Okay， so for that。

 like I mean there are a couple of ways to think about how to extract a solution to the original problem。

 for example， for max cut， we use this half hyperplane rounding。

 we use the geometry and use hyperplane rounding。But what seems to be more generally plus more useful is the approach based on duality so first let's just forget about SDps for a moment and think about duality again Okay so i'm sure you' have seen duality。

In your earlier classes for linear programs。So let's just revisit to what it means。So okay。

 so duality and for the moment， let's just say you have a linear program。A linear program。It's。

 it's just。EI X。Less than equal to B。4 I equal to1 through m。Okay。

 so that's the linear program you have。And， and。Typically。

 we talk about duality in the context of optimization， but there is a sort of a more。

Something more broader that's going on and that's the idea of duality and proofs right duality versus proofs and so let me say what this is。

Okay， so let's say have these constraints， so these constraints。

Together identify some region of space， so there's some polytope。So there' is a polytop P。

That is identified by just these constraints。He， this is the feasible region。Of the LP。Okay。

 and so in some sense， if I tell you。If I show you a point。Why。In this feasible region。

If y is in a feasible region。What the body do。B。The only facts that you really know about why are。

The constraints of the linear program。So the only facts that you know about why are these constraints？

Okay， so in terms of what you know about why these are your axioms。

These are the only facts that you know about why。In general。

 for an arbitrary point in the feasible region。Okay。

 now you could ask are there any other properties of y that are true， for example。

 you could ask oh okay， is y1 plus y2 always greater than7？

Okay or any other statement about why in terms of as a linear inequality so let's think about only statements that are linear inequalities。

 so if you have a general statement let me say。C and D， so C in a product Y is less than equal to D。

 and you can ask is this true？喂。And。So let's say you have a true statement， suppose。

Suppose it is true that C in a product y is less than equal to D， and if concretely。

 let's say y1 plus y2 is actually less than equal to7 for all solutions y。Okay。

 if you have any such a true statement that holds for all feasible solutions， why。

 you can ask how do you prove it？Can you prove it then just in terms of a certificate？Okay。

 so how do you I mean in in general， how do you prove such a statement about why well。

 you can you have the axioms here， these are the axioms that you know are true and you you know。

 just as any proof， you start with the axioms and you。

Combine them to produce new statements so for example you could you know。

 if you want to derive a new statement， you can take your axiom A1 dot y less than equal to B1。

And then multipied by some two and then take it。A2 dot y。Less than equal to B 2。

And multiied by three， you know， whatever some non negative numbers like this and。

You will get a new statement。This gives you the statement。

 you got a proof that 2 a1 plus 3 a2 inapp y。Is less than equal to 2 b1 plus 3 b2 it's a new statement that you got by taking the exams and taking a non negative linear combination to produce a new statement。

Okay。So this is one way in which you could prove new statements。Okay， and。就。In some sense。

 you have a。So taking non negative linear combinations。Of your or exams。Is a way to。Blue。

New statements， right？系。Okay， so so in some sense， you have a little proof system here。

You have a little set of rules that you could use if you have a statement。

 I mean if you want to formally write down the proof system in some sense you have， I mean。

 I guess this is one。Okay， right。嗯。Okay I'm trying to see if I can get the notation right like you know proof systems you know are based on some set of rules right so for example。

 if you have statement S1 and statement S2， then you can derive statement S1 plus S2。Okay。

 and then if a statement S1， then you can derive a times S1。Well for all a non negative。Okay。

 these are the rules that you have and you can use these rules on your axioms to produce a proof right and you know these rules are an overkill really what you can do is take your axioms and take your nonne combination of your axioms。

Okay， so the only thing you can do is take your axioms and take non negative combinations of your aoms。

And the reason you want your coefficients here to be non negative is because if you multiply an inequality by a negative number。

 the inequality flips， so you would want all your coefficients to be non negative。

But so this is your proof system， non negative combinations of axioms taking。Okay。

 now if you have any proof system like this， you know。

 there are usually the two main things that you want to prove to ask about a proof system is the first thing is。

Its a very weak thing。诶。It's called soundness， so soundness says every statement that you prove is true。

Every statement。That is pude。Is actually true。Okay， and this is not， I mean。

 this is sort of trivially the case for us because we're working in the world of leader inequalities and you know。

 you're not going to。嗯。I mean， these are so obvious in this case。

The proof system is so fundamental and obvious this is really math threat inequalities。

 So it's going to be sound。 So this is not a but if you talking about a general proof system where you give a bunch of rules to derive new statements。

 this is what it means to be say the proof system is sound。Okay， and if you think about it。

 this is really what weak duality is。I when we talk about weak dual of linear program。

 that's really saying that this proof system that you have is sound， which is。You know。

Quite obvious in some sense。I guess the more interesting or more stronger property。

 which is also true。Not always， but in some proof systems and in particular in our case here is a completeness。

Every true statement can be proved。Okay， so what that is saying is this is strong duality。

 this is really strong duality。So。Just in like for linear your programs。So what's the context here。

 so if you had what it is saying is if。So basically， y1 plus y2 is greater equald 7 for all y。

Feasible。Okay， a statement like this is true。If on the if。

There exists some set of non negative numbers， C1 through CM。Such that。

If I look at this inequality that I get by。Just multiplying my axioms width。I take my。

And okay let me just flip the sign here， otherwise I have to。Work with minus11。

So something like this is true， y plus y2 is less n7 is true。

 if I don onlyt leave there exists non negative numbers so that if I take the linear combination of magxioms with those non negative coefficients。

 I will get the inequality y1 plus y2 is less n or7。Yeah。So this is strong reality and that's the。

 I mean that's critically that's one of the most important facts about linear programs that as a proof system that are complete。

 any true statement is actually provable by taking non negative linear combinations。Okay。

 and this is， you know， usually you talk about optimization， but when you talk about optimization。

 like you're really what you're。What you're doing just to show what's happening there。Is。You like。

 you know， to connect it back to the usual things， so imagine you had maximizeization。

 maximize y1 plus y2。Okay， and then you have。E。Y less than equal to B I for all。

 I equal to1 through M。Okay， and if you write down the duall for this。要车。嗯。Well， okay。

 the formerly the dual would look like。Minimize。Submission， C， I， BI。十只度。😔，嗯。

Let me call this D in aor y。啲。So great。Okay this are your write duals for I。

Lineer programs right I mean it's not important The details here not important。

 but really effectively what you're trying to do when you write a dual is you're trying to find。诶。

A some square sorry not some a non negative combination proof from your axioms of an upper bound。

So in this case， you， let's say your objective function was y1 plus y2。And。

What you're looking for is proof that。The objective value is less than seven。

Using your axiom seal combination。Okay， and if you want like that's a feasibility version。

If you're in an optimization version， you ask what is the largest value of the y1 plus y2 for which I can still prove an upper bound like this。

 and that's what usually dual linear programs and they usually mean。But the key thing to remember。

 I mean， sort of take back from this is just this fact that on polytopes or。

Basically in feasible regions of linear programs。Every linear inequality that is true can be proved by this technique。

And。That's the key thing to remember， and that's really what strong reality is。

So there's a connection and you know what a dual linear program is doing is really finding the proof for you。

 it's looking at what is the combination of what's the values of the CIs that will give you the proof so dual linear program is really finding the proof and strong duality is saying there exists a proof always so that the dual well optimum and the primal optimum match always。

Okay， so that's very important concept that's clear。Okay， so this is a。嗯。Okay， this is good。

 all right so。You know this。Yeah。Right， right， so this。嗯。This idea of proofs versus。

ComYou know proof systems and their completeness is sort of a very。

Like very fundamental thing which shows a all over， for example。Okay。

 when we go to polynomial systems still not going to SDps yet。

 but let's say you just look at polynomial systems of equalities， so suppose I tell you that。

I don't know。嗯。A plus B。I can't hear the professor。哦。It's good now， it's good now， Okay， yes。

Let me see if I can do something about it。Before it goes back。Okay。Yeah， let's。All right。

 so I was saying。You know this notion of idea of what can you prove and what statements are true and what can you prove is a very fundamental thing that shows up all over math and it's a very basic thing so here's another example。

 so imagine I just gave you a system of polynomial equations。So is a polynomial system？Of equations。

So let's say I ask you。Okay， I give you P1 no thanks。Equal to0。P2 of x equal to 0。Pm of x equal to 0。

Okay， and I said these are your axioms。This is what you know about X。I ask you。

 isq of x equal to zero？And or let's say。Suppose the following is true。 Suppose it is true that。To。

Let me call this polynom system P。For all X satisfying。This problem in system P。Suppose it turns out。

That Q of x is also equal to 0。Okay。So in some sense， k of x equal to0 is a true statement。

 that's what I'm saying， it's a true statement。Alright， then I can ask，オケー can。How can you prove it？

Like when can you prove it and how can you prove it。

 is it possible to prove such a statement at all or give a certificate of such a statement？

And this being， I mean it's a age old it's a this has been asked like 100 years ago。

 I guess maybe 1 20 years ago on math and in particular like you you could ask can you use algebraic？

This manipulation to show that Q of x equal to 0。For example。You could say， oh， maybe I can write。

K effects。As a linear combination of。P of x。Okay， this would be a proof。

 this should be a certificate。Well okay why do we say these thing why do we call these things proofs or certificates the reason we call them proof certificates of course you know we intuitively feel like theres a proof。

 but the other reason is also there's a more concrete way to say what is it's a proof is an NP statement is something that's in NP meaning it's not just that。

This is a proof if you think about computational you can actually check this proof like suppose if somebody gives you the Rris。

 how do you check this you just。Multiply out these polynomials and you check that that's equal to Q of x so proof is something that's easy to check and so these are certificates easy to check。

Right。And that's the。Right， so。They are easy to check， the key point is they're easy to check。啊要。

Whereas a statement， whetherq of x is equal to zero whenever pi of P1 through Pm of x equal to0。

That statement is true， but it's hard to check。But if I tell you that P。

 these things imply Q you have no way to check that apart from checking all the solutions or something。

 solving the system yourself， this is a certificate so okay。

 so so now you have a I mean the question is can you do have a certificate like this。

Well it would not necessarily be。But， you know， the。

General statement is that it's called the Hilbert New still and starts。Is that？

Like something like this is true， as in you can there exists some。Power。

 let's there is some Q x to the power C。So' a kx to the power C is actually equal to sum or i equal to1 through M。

R I of x times Pi of x。So this is a proof now。That peak， this you know once you see such an identity。

 you know thatq of x is equal to zero。When， whenever。Oh。X satfies speed。

And what Hilbert nuisance has say is that this always exist such a proof whenever a statement is true。

 there is such a proof。Okay， so， so that's。Very nice。 I mean， of course， it doesn't give you any。

Any sort of bound on this consttuency？Or like any bound on the degree of these polynomials。Okay。

 note that once you have， if I told you a bound on the degree of these polynomials。

 if I told you that there exists is a proof in degree D。

You can actually find the proof efficiently because you can just solve the linear system。Right so。嗯。

一费。If this is degree D。Okay， if every term is delete， then you you know。

 finding the proof is just finding， you know you can solve it， you can do it。Okay so。All right。

 so where is this going well now we're talking about polynommal systems with equalalities。

 the next thing is inequalities， so suppose I have a polynommal system with inequalities。

So I have pi of x greater equal to 0。For I equal to1 through M。Okay， now you can ask。This is B。Does。

P imply another inequality， let's say Q of x grade equalel zero。Okay。They are alternate， suppose。

Suppose p of x p impliesq of x greater equal equal to  zero。How can you prove it？So。This is where。

 okay， so now we're trying to prove something different。

 we're trying to proverun any inequality of the formq of x greater equal zero。Okay， so。

How does one prove that some polynomial is greater equal to zero？Well。

The most natural thing you can hope for is that K。Is actually equal to。Let's say， for example。

 a square of a polynomial。If I show you Q of x is at least the square of a polynomial。

 then of course， you know that it's greater equal to zero。Right。

More generally I could show you that Q of x is actually a sum of squares of polynomics。

So I could maybe show that Q of x is actually equal to sum or i equal to one through， I don't know。

And capital n something iss squared of x。If I show this identity。

 of course you know thatq of x is going equal0。But you know。

 this identity still doesn't use your axioms yet。This is just true if any polynomial which I size squared rank or zero。

 of course it's。If any polymer with sum square， it's greater equal0， so we want。

If you are to use the examxioms， how would you use the examoms？Well， you。

Suppose I showed you an identity of the following form。Q of x is sum of squares plus。嗯。

Some over other terms like Ij equal to1 through M。Of P of x。Timemes。Another sum of squares。

I don't know， let me call Jake。啊 i知。Squared of x。So， basically。Yeah。This is a SOOS polynomial。

 an SOos polynomial， let's say， is a sum of squares polynomial。So this is aque polynomial。

This is also a Samqueash polynomial。And you know that PiI of x is greater than equal to zero that's by your axioms。

So since each term here is non negative。The first term is almost course non negative。

 the coefficients of P are non negative and P themselves are non negative。

 So the whole thing is non negative。 So this proves to you that Q of x is greater equal0。

If I show you an identity like this， that's an actual proof that。Q of x greater 0。

Well professorfesor， yes， is it everything like S squared plus like the sum j equals one through around。

 all that like within the outer sum over I， right？2。Andm sorry could you repeat。

 what do you say Like is the like function that you sum over I like the entire。

Like the entire expression like S squared x plus like the sum over J no， I was thinking just。Yeah。

We said what， wait what is？Where's the eye like in the second thumb then if eyes oh oh sorry。

 I should okay， I should use。Jake， right， so this will。Yeah， I shouldn't call it I again， yeah。Yes。

Thanks， yeah， it should be。So there's i equal to1 through mpi of x times RIj squared of x。

So basically you're taking a coefficientfish linear combination of your axioms。

Ver coefficients are some of squares polymonmials themselves。

you allow have some correspondents as coefficients。

 and then you can add a sum correspondent at the end and the whole thing will of course be non negative because。

Every term that you added and multiplied is non negative。And therefore。

 you get a proof that pq of x grand equal0。ok， so啊。Right， so so for Hilbert Knowlster starts。

 you can compute a certificate it's just that the earth like the the most。

When the original version of Hbert No as doesn't give you a quantitative bomb on the。

Degree up to which you to look the there are more effective versions which give you an actual bound on the degree at which you'll find this。

 but that degree is really really astronomically large I don' not recall maybe even doly exponential or something so in general you can't do it efficiently。

But that's the way it should be because these problems should be and be complete， right。

If I give you a system of polynomial equations like think of three sec right so p1 of x equal to0 all of these polynomial constraints。

 these could be clauses of。嗯。Cllauses of a three sat formula。

 and then I ask some statement about the solution to that formula。

And although everything is an equation and you should be able to prove it。

 the degree of that proof should be really， really high because you can't find it such VMP complete。

走。But you do you see that you get a， in some sense you get a hierarchy of proof systems here。

 you can decide， okay I'm only going to look for degree five proofs look if you decide to look for degree five proofs then it's some linear system you can try to solve it and you can go increase your degree and look for higher and higher degree proofs。

Okay。Alright， so that。Is。Okay， so now we' are talking about summer square proofs。

 so this is what a summer square proof for a polynomal system looks like。

 so let me just give this make this a definition。Given。呃。And an a proof。That。B implies。

Some other inequality Q of x greater equal to 0。I。嗯。😊。

Or this is our definition of a Zos Square probe， let's just say it that way。Okay。

 this is going to be our definition of some square proof for it。我近。想 let me just say。And callll this。

It's not of X。Plus， some over。B I F X， S， I F X。I equal to1 through M。Where。Each is not as one。S M。A。

SOS polynomials。So by so polynoials， I mean， they are sum of squares polynomials。

And the degree of this proof is basically。Let's say the degree of any term that you encounter in the proof right so the degree of all the polynomials。

The max degree of all the polynomous that you encounter。That's the degree of dis proof。

Because that's what determines here complexity。Maximum of these degrees。Okay。All right。

 so okay now the natural question is does there always exist a sum square proof this yes。

 there is always a sum square proof with a slight twist。So Hilbert， I guess it's not called Hilbert。

 it's just called positive st starts。波司刀。Stling。Ss。

I I'm going to boots maybe the spelling posture and insert is what？Well， basically， it says that。

They always exists。And then so is proof。That。You know you。嗯。As so ass proof that you know。

You want to prove that P in place。You want to prove that P impliesq of x greater and equals 0。

What you'll see find is an identity which is slightly different than what we write here。

You allow yourself multiplication by a poly。Okay， one plus。うん。Art effects。是。So this is an SSS。不能。

Because there if if。And these are all less problems here。

So note that if you see an identity like this， it certifies thatq of x is grade equal zero whenever P of grade equal zero。

And what positive students had say is that there's always such a proof。Okay， again。

 there's no bound on the degree， you know it's just there's no useful bound on the degree。

It could be really， really large。Okay， so anyway， okay， so。Allright， so we've been talking about。

Proof systems and a little bit of duality。嗯。And we saw how LP duality is got with a certain kind of proofs。

Now， let's look at。A a source proof system and SDDP and semi differentite programming duality。

 and what we'll see is that the dual objects there are really some square proofs。Okay。

 so that's what we'll see。Okay， so to do that， let's just first see how to write duals for a semi different program。

Okay， so let's start with a simple SDP。So Max cut SDP。And write it not in the vector word。

 but in the as a linear program or PSD matrices。So what are you maximizing you're maximizing？

Some linear function。So I'm going to write this as L comma x。

It's not super important what the form of the objective function is。

 but it's a linear function of the matrix entries。对。And we have some constraints in our program。

XIi equal to one。Okay， so to simplify our life， let' just I mean， simplify our life of writing duals。

 let just as you make less than equal to one here instead of equal to one。

I don't think it's not a big difference just for all i equal to one3 m。1 to n。Okay。

 and the final important constraint when you write a max cutvP is a Texas positive semiul Fnet。

This is X is PSD。Okay， so this is a semi different program and how do we write a dual for this？嗯。

I mean， you can develop the whole thing in general for convicx programs you can talk of duals。

 but what we'll do now is we'll just use like a。嗯。You know， we sort of。

Appeed to things that we know already very well， which is writing duals for linear programs。

So this thing looks like a。Linear program， it has a linear constraint。

 It has these linear linear objective， linear constraints， except for this extra。

Positive semidefiniteness constraint。But a positive and effectivenessness constraint， if you recall。

 is you know， let me just， you can it's just。Union of infinite intersection of infinitely many linear constraints。

 so just to recall the definition of a PSD matrix， a matrix x is PSD。All right， is PSD。

That's what means if and only if。For all vectors v， v transpose xv is greater equal to 0。Right。

 that's the definition of PSD matrix。 So instead of thinking about X PhD here。

 let's just think about。Infinitely many。And LP with infinitely many constraints。

 so I'm going to have you know we transpose。X v。For all is grade equal zero。For all vectors。

 B not again。O。So， that's a。So it's a linear program with infinitely many linear constraints。

 but you we can still try to do the same exercise of how we write dualls for linear programs。

So this to the same exercise and it will get the right answer。Okay。

 so in order to write this more as a。Liner program， let me。Let me rewrite this。

Constraint a little bit better。Actually， let me just rewrite the whole program so that it's sort of clear。

So here's the whole program。Maximize。L in the product X。subject to。嗯。I guess， yeah。

XI less than equal to  one。And then。X is PhD is saying that for every vector we you have this。

 so let me just write it， write the constraint so for every vector we。In order to the end。

I have a constraint。声。嗯。Negative VV transpose in a protex。Is less than equal to 0。

Right so here what we're doing is we're writing the just looking at the dual for max cut dual for the max cut SDP and you can do the same exercise for any SDP that you want。

To write a you。Okay， so。Okay so these are infinitely many constraints here it doesn't matter just go ahead with exercise so what do you do when you write tools for linear programs you introduce one variable for every constraint that you have okay so here Ill have。

One variable for each of these constraints， let me call that variable alpha I。

And then there'd be one variable for each of these vector constraints。

So there are infinitely many variables， I mean things don't matter here， so it betterta V。ok。

All right， so then。Okay， these are my dual variables， my dual variables are alpha I and be vs。Okay。

 so then you can check。What you're doing is you minimize。三。Over I alpha I。Okay， and。Subject to。嗯。

What do you want？嗯。Yeah， you know what， actually。Let's not write sorry yeah let's not write duals in this old way of maximization minimization always confuses me little bit let's I just like let's just think in terms of our。

You know。Proving upper bounds， right a linear program。What is it trying to do。

 you're trying to maximize it。Okay， what is a duall trying to do。

 it's trying to prove an upper bound on it， so it will try to prove to you that Lx is less than equal to B。

Well try to prove that。Some value， let's say B。Minus L。Is grade equal zero。

 you'll try to prove this statement here。And what how will that tool try to prove the statement to you。

 it'll take all the inequalities that you gave it and it'll try to take a non negative linear combination of that。

So in this case， you just say。Okay， so these are the inequalities that it has it has these Xile less than one for all equal to one through and and has this infinitely many other inequalities at disposal it is just going to take a non negative linear accumulation of them so it's going to。

四。Some over I equal to one through。And。Alpha I times。1 minus X I。

And then right that's what's greater equals0。And then。Plus。

Some over all possible vectors v of beta v。keep出情度。Okay，嗯。Soれ嘅。

I keep switching the direction of inequalities in this profile， unfortunately。

 so this is clearly Xile lesson than equal equal to one。But I think it's。

Let me just say B we transpose。Soly from that， yeah。I mean。

 it's the same thing just whether you yeah。You want to take non negative linear combinations。

 so this gives you this is grade equal zero and then this inequality times。

V we transpose in a protex。Okay， so the LP knows that1 minus X is greater and equals zero。

 the LP knows that Bv transpos a proex is greater equal these are your axioms and it's taking a non nonlinear combination to derive the fact that you want to derive okay that's what the LP is going to do the dualLLP。

Well， the dual LP is the dual SDDP in this case。So what is the dualLSDP here， let me just write it。

So， it。Just to copy this inequality again。the next page。够。Okay， so some are equal to1 through n。

Alpha i times 1 minus X。Glas。I'm just going to。Push this sum or things inside some over we beta v B we transpose。

Inner productex。Okay， so that's the other。That's the dual LP。Dl LP。

 the duall LP or duall SDP is trying to find these alpha I and this。Matrix here。Okay。

 so what do we know about this matrix。 So firstly， it's an infinite sum as I've written it。

 but that's sort of， you know， not so important， but it's really a sum of non negative terms it's sum of we we transpose non negative as it's a sum of。

Nona linear a combination of non negative rank one terms， right？

So basically here's another statement about PSD matrices， a matrix x is PSD。

 if and only if x is equal to some over some non negative coefficients。Right C， VI， VI transpose。

It and。Every non negative combination of rank terms is PSD and vice versa every PSD matrix is some of non negative rank terms so instead of talking about some of beta v we we transpose I can just call it something else just any matrix that PSD is fine so let's call this some other matrix。

嗯嗯。Let me call it why。哎呀。Okay， so something important happened here。

 but we'll come back to that so basically what so the SDP now。The dualLSDP。

 if you had to think about the dualLSDP。Would be。嗯。Right， find。嗯。Alpha 1 through alpha n。And the P。

 okay， these are numbers。 These are non negative numbers and。PSD matrix y。a PSD matrix。Such that。

B minus。It gives you an upward bound of B on your SDP value。Like this identity holds。So one thing。

 if it's confusing， one thing I want to emphasize here is in this identity， these x's。

Are the indeterminants。Indeterminateants， as in they are the variables in this linear program that we had right this infinite size so these are the indetermates。

And。嗯嗯。The alpha I's and the beta vs， they prove this identity on these indeterminants。

They have the variables and this is the identity the alphaphas and beta v prove on this。你他。嘅 in。

Any question on this？I mean， one thing that sort of happened here。

 which is not so important for what we're going to talk about next。Is just that。

When we took the duall of the SDP。We got another SDP。

We had this infinite sum sum over beta we transpose。That's the dual cone。

 that's the dual object to a PSD cone， but that turns out to be also the PSD matrix right saying that something is a sum over beta B we we transpose where beta vs are non negative is exactly the same as saying that matrix is PSD。

So this is got to be the fact that the dual cone of the PSD matrices is also the PSD matrices。

But forget about the terminology of dual cones and so on， we didn't get into the duality there but。

That's what it is if you want to figure it out。So okay。

 this is the dualLSDP right so that's fine for what we're going to do next。

 the form of the dualSDP itself is not so important。

What's important is just like conceptually what is。What is the dualLSDP。Finding for us。

It's finding this identity， right？It's finding us this identity。Okay， now that's good so。

Now let's interpret this identity。In terms of。The。In terms of the。诶。

In terms of the original SDP that we had， remember that this identity is proving us an upper bound on the value of max cut。

So let's just write down what every term here is， Okay， so firstly。So if you recall。嗯。X。X。

Was the original matrix of Xjs， and that is really the moment matrix。Of solutions。To max cut， right。

 this is a moment matrix of solutions to Mac。 That's what X was in our original max cut S DP。

 So and what is what was the objective function， Let's write down the entire expression here in terms of the original polynomials that we have。

So the objective function in max cut。Hel in a pertex， this corresponds to the polynomial some。

 I mean， this was the objective function in max cut， some over all the edges。哦 I I did。

X is X holds square， right that's worth。That was。Okay， and。X AI。Remember。

 Xi actually corresponded to the monoomial X squared。In fact， XA。Is。Like in the SDP。

 XII was actually supposed to be。The pseudo expectation or the pseudo expectation of Xi squared。Okay。

 and what is。V we transpose X。V we transposing a paradex。This is nothing but v transpose Xv。

That's what it is and what is that？Well， if。it's just some other idea。VI v j。Exhaed。

And that's what we transpose XV is。Well， what is that Well， it's we。I mean， it's just some over I。

VI v j。一定的。😔，X， I， X G。That's just what Xite J is。Okay， and this is nothing but。

E tilde of sum or I V I X I whole squared。So all I'm doing right now is I in the we have this。

Dual of the SDP that we wrote， we thought of the SDP as an infinitely large linear program and we wrote down its。

LD LP， and that's what we have。 And what I'm going back to。The world of polynomials。

 because remember in our degree D SOSSDP or degree2 SSGP。

The entries of the matrix x were actually expectations of polynomials right Xi was E tilda Xi squared Xj was Eilda X Xj and so on right so Lina proex is E tilda X minus x squared。

Okay， so， okay， so what's the dual doing now Well the dual is just doing the。foring。

In the world of polynomials， it's finding us this sort of a。Think you have。

You have the max cut objective value。It's trying to。Rightrite down。An identity of this formed。

That its trying to find an identity like this。In the world of Ponomous。

 the dualL SDP is really just finding us a SS proof。What is SS proof？Well。

 these are non negative so what's well。Well， it's trying to find as an identity of the form b minus sum over ij in Exi minus Xj whole squared is equal to sum over I alpha I1 minus X squared。

Plus， sum over V beta v。I VI X I holds square。Okay， this is a summer square proof now， right because。

If I write if I showed you an identity like this。It shows that this term is non negative。

It shows that this term is non negative。And therefore。

 it proves to you that this term is non negative， meaning that the objective value。

Is always at most be。So starting with the axioms， one minus excess quite greater and equal to zero。

It's giving you a summer square proof。And it's a degree2 sum square proof the reason it's degree2 is because we only had degree two moments in our X Ij。

In exc when had degree two moments， so therefore every term that when we wrote down。

 it was utmost a degree2 polynomial。ok， so诶。So。Basically the duall。Of the degree D。

SOS SSZP that we wrote last time。The duall of that is basically finds a degree D。SOS S proof。

That's what it's trying to find。A dual of a degree resource EP finds a degree resource proof。Okay。

 and again。So it's a restricted proof system as you increase the degree。

 it's looking at SS proof of higher and higher degrees。But。For any fixed D， its power is restricted。

 not every statement that is true can be proved using a degree DS or S proof。

You might need a higher degree to prove a statement。嗯。And that's why。嗯。The value won't be like like。

For example， the objective value won't be exactly equal to the correct answer until you increase the degree to be sufficiently large。

Any questions on this？这里。Okay， so。但。Bto诶。Okay， so we， we have a。诶。

We have a definition of a SOOS proof。Here， okay， and let me write down the definition of a pseudo expectation and basically the main claim or the weak duality claim which lets us analyze pseudo expectations okay。

 so it's basically what summarizing what we discussed so far。Conceptualally。

 the discussion has been around。SS write proofs and the dual objects through expectations。

 but let me just formally state the thing that we would sort of use sort of succinctly。Clear， okay。

 so we've been talking about pseudo expectations。 So here's a definition right。

I don't think I've very formally defined it。Last time。Deggree D so of expectation。你听的。

It is a linear functional that maps。Dgree deep poly nos。Two real numbers。The linear functional。Okay。

 that's what a degree de expectation is。And。With with the proper。

For if I say DVD should expectation for a polynomial system。Or。PI F x grade equal to 0。衣服。

Then it must satisfy the following properties， firstly itilde of PI effects。Should be。

Great equal to 0。For all， I equal to1 through m。Actually， let's say even something stronger。

Itil up pi of x times s squared of x is greater and equal to 0 for all equal to13M。

So if I give it a polynomial which is P of x and this square of think。

 which should be greater equal zero。And the second statement is。Eil the of。嗯。

Like a square poly should be greater equal zero， right that's， of course implied。嗯。

And let's say Eilda 1 is one。Just a constant function it maps to one。

So a degreeD expectation is a linear functional。Whi given any polynomial output serial real number。

 which satises these properties。Okay， and。When we solve a degree SOS SSSGP。It outputs。

 it gives you a degree D sugar expectation。Okay， these are the primal objects。

 like these are primal SDP objects。The duall of this is。Like the dual SDdP that is really。

Fight summerqua troops。Right。When you look at the dual of the SSDP。

 it's trying to find some square proofs。Okay， and the statement of weak duality that I am going to use is just going to be。

 we won't need strong duality for some。Sometimes we just look at weak duality weak duality is this very simple statement that。

If。Let's say I have a sumosque has proof thatq of x is greater equal to zero。If。Ko effects。

Grade equal  zero admits。A degree D so S proof。in the sense that we described earlier。

 so Q of x is equal to some company。His。S0 squared of x。😔，So as zero。We have this S0 effects。

Plus sum over S effects， EI effects。电视器。P implies k of x gra equal0。This admits a some square proof。

Such as。Like this then。For every。Dgree D pseudo expectation。一定了。Eilde of Q of x。Is great number to 0。

Okay，'s quite you know， it's a little bit wordy， but what it's saying is something very， very simple。

诶。All it's saying is that。If you prove some fact like Q of x greater equal to zero using a degree d sum squared proof。

Then that fact is also true for the。Solution that you get out of the。SDP。Okay。

 this is a I mean quite wordy， but it's sort of really。

 really basic simple factor like you remember for LPs in the world of LPs is just this。

Very simple fact if you prove some fact by taking a linear combination of your axioms。

Okay you took linear combination of these exams and proved this fact。

 then of course that fact is also true for every LP solution satisfying those constraints。Okay。

 that's just what it is。And this is exactly what you're saying。 if you prove some fact using。

DgrD sum square proof that fact is also true for the E tda of kofx， meaning the SDP solution。Ally。

 the SDP can cheat。The SDP will give you。sudo expectations which are pseudo moments。

 there's no real distribution you know and could be there's no there's no real solution for vertex cover but it gives you some values which don't mean anything。

 but the values still have to satisfy some constraints in particular if you prove a fact using SS proof that fact is also true for the SDP solution。

Okay， and so if you have a but the one key thing is the way you prove your fact should be。

You should prove it using a degree DOS S proof。系。That's the key thing。If you have a simple proof。

 let's call a low degree proof as a simple proof， if you have a simple proof of a claim that then that claim also holds in the pseudo world of SDP solutions。

In the real world of actual solutions， anything that you prove using whatever technique you use。

 like you could use whatever technique outside of algebra， anything that you prove is of course true。

But in the world of SDP solutions。Anything that you pro using。

Deggree D SOS SDDP proof actually is true for the SDP solution。Okay。

 that's the weak dual strong dual is to say the reverses。

 anything that's any fact that's true for certain expectations can be proved using degree service proofs。

And strong du is mostly true in most cases you care about， but you have to be careful。

But we want a strong reality。嗯。Any questions？Okay， so。So just to say where this is leading us。

The next class， we will look at algorithms based on SORS SDDP。

And the way we analyze such an algorithm is， so let's take some problem。

 let's take a concrete problem。Okay， let's look at the。嗯。Okay。

 let's take we take some problem and let's let me describe the problem next class。

 but let's say you take a problem linear regression。Okay， we will write a polynomial system。B。

For linear regression。Okay then of course every poly system that you write down is most likely going to be NP complete to solve exactly。

 so instead you solve a degree D SSDP for it。Okay and the degree SS is if you will just return some moments to you。

 it will just give you E t of right it'll give you this Eil dixii xj。

 it will give you all the moments。Okay。Now you need to show that these moments actually give you the solution to the problem that you care about。

 which is linear regression。So what do you do？You basically want to prove a claim about SDP solutions。

And to prove a claim about SDP solutions。you appeal to this fact？We will prove。Using low degree SOS。

主。So this is basically algebra， you're doing algebra， but you're restricting yourself to low degree。

Youroving a low degree so as proof that。Any solution to P。Is close to the true answer。

Clloose to through the answer that you care about。The true answer they care about。关主。

But since you've proved， this is a loading resource source proof。I will imply that。

Solution returned by the SDP， the Eda。Values are also close to true answer。

Okay that will be the strategy， so we want to prove a statement about Eilda。

You want to show that SDP gives numbers that are like once you solve SDP you get the right answer and the way we prove that we get the right answer is well actually prove that any solution to original polynomial system is the right answer。

And we'll prove it using a low degree SS proof。And thatll imply that。でデピ。Values。

 Eilda values are also closer true answer。So you know at this point this seems like a might seem a little bit too abstract itll become very concrete next class will I' write on a specific polynomal system for linear regression。

 robust linear regression and we will。Do four lines a few lines of algebra。

To prove some statement about that。And since the proof， algebraic proof is low degree。

It'll immediately tell you that the SP gives you the right answer that you look for。So嗯。

Any questions on this？we not use that。In real life to solve linear regression since we know other algorithms for it。

So we well I mean of course we won't do linear regression we do I mean linear regression will be too simple so well do robust linear regression so the problem that we look at is。

I give you end points， out of which one man is epsilon and are explained by a linear function and some epsilon fraction of them are adversarial。

Then， you know， of course， you're use great inent not in that case and then。Yeah。

Like it's robust linear regression， well look at a problem which you can't just solve by gradientcent robust linear regression。

Which is a bunch of outliers， really aggression trends of outliers。

But I mean we look at that problem or we look at another problem also。

 but I guess the this is the part， I mean today was quite a bit conceptual。But。Yeah。

Like this conceptual thing is what is basically like the compiler of the sort of Python language that have been promising people。

 so it's like the compiler， right， it's like the internals of what's going to happen。

Like when you design an algorithm， you will use。You will basically be finding a sum square proof if you're doing some algebra。

 which this compiler will compile it into claiming that the SDP returns the right answer。Okay， so。

So the language in which we analyze the algorithms is you know as algebra， know you do algebra。

 you're trying to find algebra， you're trying to find algebraically prove things。He be more clear。

Next class， Michael yeah。对。Thank you， Professor。

![](img/e46a987a7fb34cd32ed9a6611dbe282c_2.png)

![](img/e46a987a7fb34cd32ed9a6611dbe282c_3.png)