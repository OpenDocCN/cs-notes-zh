# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p27 Lecture_27_The_Sum_of_Squares_Paradigm.zh_en -BV1a4cCeMEzb_p27-

So， maybe let's。Let's get started。 Welcome back， everybody。And。Welcome back to lecture 27， the。

 the last of your federally mandated lectures， not federally mandated or whatever。

But we will have two more lectures。 there'll be one on Wednesday。 I was trying to have one on Friday。

 but unfortunately， I need to travel last minute， so I'll have one next Monday。😊，And hopefully。

 we'll cover whatever material we want to cover and we'll see how it goes。Okay， so this is。

 but this is the first of the， you know， listeners choice lectures and the topic is the sum of squares paradigm。

😊，And I'll tell you a bunch of stuff about this。 One thing I should mention is I'm not the local expert on Samsa Squares。

 Provesh Coari is。 So Im I'm like the the guy who's been practicing in front of the mirror and how to say somesa squares and words like that。

 but I'll give you my perspective on how I think of somesa squares。 It's a very very clean idea。

 In fact there。😊，At least two stories。 one can tell about this。 And today。

 lecture will be essentially a。You know， trying to strike a happy balance between the two stories。So。

 so okay， so so let's get started。 So here is， here is the big question that we want to answer。

 I'm given a polynomial P of x And P of x， X is a vector。 So whenever I write x out here。

 x will be a vector。 and it's， it's an object of the following form sum over I is a j into J of。😊。

1 minus X， I， X J。Over。Squared over 4。Let's say subject2， I'm saying X is squared is equal to X。

For line。Okay， and X is real value， right。😊，Now， this， you'll realize is the max cut problem。

X squared is equal to no， So X squared is equal to one。This is the max cut problem。

Because these constraints are really saying x is either plus 1 or -1。

And this is counting one every time the two have different parity。This is Max cut。

So I am trying to solve so p of x was this polynomial and so basically what Im trying to solve is I'm trying to solve a problem of the following forms。

 this is a polynomial now。Max B of fix。Such that。And now， let's say that I have a bunch of。

Polynomial G of x， which I say is equal to 0。So here， G I of x is X squared -1。It's a polynomial。

 I'm saying this is equal to 0 for all。This is a bunch of polynomial equalities。And I'm saying。

 maximize this quantity subject to this。Captures max cut。This is a special case of this problem。B个。

This is。Maximize。I could also have， you know， I could make the problem more difficult by saying F J of x。

Is greater than equal to0。Forology。So I I'm looking only at the x's where this。

 the equalityities are satisfied and the inequalities are satisfied。😊。

If you were just working on equal， this is known as a variety， I think， an algebraic variety。

With these things， it is no longer an algebraic variety It often called I learned this recently。

 this is a semi algebraic site。😊，And I'll call it K， even though it's not really it's， you know。

 in we are getting away from standard convention that K convex in this case。 what's that。So x。

 all these are vectors。行。So， so exactly。 So all these。 And basically， I'm saying。P。

 F and G are polynomials， lets。Of degree。This is what I'm interested in。

Is this very rich and powerful。Moring language。Okay。So in general， I'm asking the question。 I'm。

 I'm asking a very broad question。 And， you know， you should be worried， this is all N hard。

 What algorithms could I possibly give。S，OS。啊。What were you saying about？Just usually a K for me。

 the con accept。But in this one it's not。 So let's actually look at this thing。😊，So。

 so let's look at this set。The only points would satisfy this。Are the points in So So here。

 K is equal to negative 1，1 to the n。It's not connected。 It's not convex。 It's not， you know。

 it's a discrete set of points。So it could be completely crazy。 It's， you know， some， some， some。

 it could be a manifold。 It could be just a discrete set of points。

This is the object that I'm interested in。And I'm asking。

 I want to maximize this polynomial over this sec。Okay。When， how can I do this。It's very powerful。

Language， Im asking。 of course， I'll get hardness。But when can I avoid hardness。

What results could I possibly say？ThisThis is the kind of questions I want to ask。What do we know。So。

 let's get back to。The degree D equals one。This is our nice case。 This is the case we love， right。

What am I trying to doing， I'm trying to maximize C transpose x such that A X。Moし边。Each of the。

 you know， I'm going to write this as。F I of x。Is greater than equal to 0。

These are linear polynomials。Right。F1 of x is a transpose X minus Bs。Or B minus a transpose x。

 because I had said less than equal B minus B1 minus a1 transpose x。Lineal polynommal。O。

This is a case where these guys are linear。So this is P of X。你 are连年。I could also have G J of X。

Is equal to 0。All linear。We know how to solve this， right。This is the easy part of the board。

 That is the hard part of the board where D is at least2。 this is d is equal to one。😊，Okay。

And we have these beautiful theorems out here。Okay， what kind of beautiful the， We have strong dual。

Okay。What does strong duality says， I'm going to write strong duality in a way that we didn't really talk about in lectures。

 I'm going to write it in the form of farcas lemonma。What does Farkaius Lamma say。

 If you don't remember it。 It's O， Ill tell you what Farka lema says。😊。

So for Ka Lama let me just write， you know， this is too abstract sometimes。 So let me just say。

 I want to maximize。Let me not even worry about maximizing。 I want to understand。Given。A X。

Is going to be。At least。At most， be。I have this is， you know。

 this is a bunch of linear inequality constraints。 I want to check whether this is empty or not。

I want to just check feasibility。The simplest case。喂。What does Farkaius Lama says。Exactly。

 one of the following two happens。Exactly one of the。Following。Happens。That exists in X， such that。

A x。Is less than equal to B。O。That exists。 So why。Not negative。Okay。Such that。Y transpose is a。

Is equal to 0。But。Y transpose B。Is equal to negative 1。Okay。What am I saying。

And I'm saying I going to take this LP。😊，Excellent what I should have written。A。

Is less than equal to B。This is what I want to。Get a solution for， right。

I'm saying I'm going to combine these inequalities。Using this why。This is non negative y。

 So if I just take all the linear inequalities and just sum them up after multiplying them by y the answer should not change。

 I mean the sign should not flip。Basically， I'm saying sumation of why I。

Times AI transpose x minus B。This quantity。I was saying it's less than equal to 0。

If I had a feasible solution， this quantity would be less than equal to0 for every eye。😊。

And I'm just po sum summing up。 you know， I'm just taking a positive combination。

 So this should be less than equal to 0。😊，If they were a feasible solution， this would be the case。

Right。And what is this thing， this is y transpose a。And what is y times。B。Is just Y transpose be。

So if I take a bunch of linear inequalities and I just sum them up。

 you know I scale them up positively， that is fine。 the inequality sign is not changing。😊。

I sum them up。 The inequality sign is not changing。 I get an inequality that is implied by this。

And that inequality phase Y transpose A， X is less than equal to y transpose B。Okay。

But suppose this is0。Then the left hand side is 0。But this guy is -1。Negative  one。

That's what Farkalam are saying。So Far Lema is saying， look， if this is not satisfiable。알프요。

You look at this and say， of course， it's not satisfiable。 How am I proving it to you。

I'm suming up the constraints。I'm saying I'll get the ver constraint out here。

But I sum of the right hand side， then I'll get negative one。

This say0 is less than equal to negative one。The only way in which this can be is if the system is inconsistent。

If you were a proof theorist， basically， what would you be saying， You would be saying， look。

Each of these inequalities are axioms of my system。

I'm trying to figure out whether the system is consistent or not。

I have just shown you that the system is inconsistent。Because you can， from this。

 you can get 0 is less than equal to negative 1。Not possible。in some sense process is speak。Good。

 So so this proof system is sound and complete。😊，It's somehow saying， look。

Any inequality you want to write， you know， maybe I'll write it in in a different way as well。

Basically， I want to say， look， I am asking you whether A X is less than equal to B， does it imply？

Alpha transpose x is less than equal to beta。What does this mean。

 A X is less than equal to B is in this case， a truly convex region。 It's a polyhedron， polytope。

 maybe in this case。In the will a polyhedron。I'm asking。

 is this statement true for every point inside this convex region。That's what this implication means。

What farash and in particular， strong duality says。Is either indeed you can achieve this。 So。

 you know， there are two cases。I do。Not。In which case， you will be able to。Basically。

 this is saying you can do this， can do this。If and only F。This alpha transpose。Can be written as。

Why transpose a。For some why。And。Beta。Can be written as Y transpose B。Plus， some quantity。

some positive constant。In fact， you know， maybe I'll get rid of positive constant。

 I'll throw in one more inequality， which I'll always assume is true。0 is less than equal to one。

In all my systems， just assume that there is the inequality，0 is less than equal to one。

Whenever you need this， you can just， you know， use this。You want to add 5 to the right side。

 Were really adding five copies of that。So my a includes something like this。 Let's just assume this。

Makes my life much easier。So what I'm saying is。If this system implies this thing。

How would you do this， You would take some combination of the the rows out here and get alpha some combination of rows some combination of the elements out here。

 get beta。谁？So if， if a inequality is inclined， it's， it's just a combination of these guys。

And this is what strong dual he says。 This is what Far Kashma says。You know。

 even if you don't get what S O S means， I want you to get what far I say。It's， it's giving this。

 this system。 and all these the various forms of the Farkaash lemma moving between these is the exercise that you'll have to do。

 I'm maybe， you know， I'm trying to give a lot in one lecture。

 But if you want to just keep one thing， just keep， remember this part。😊，For Caio glma says。

 if this system is consistent， then there is a solution。😊，That's what consistency means。

And if it's inconsistent， there's a proof like this。

 I'll get a proof that0 is less than equal to negative1， not possible。Okay， this you know。

 this keep us your mind。Are we okay with this。O， enough to take this and go on a little further。

Come on more， more than two heads should be nodding，3。I want4。



![](img/50af49263d6970da6f9ad8b0b03462e1_1.png)

So what do I want。I would love to be able to say the following thing。For systems of polynomials。

So here is what I want to say。There， there is going to be false。So呃。Yeah。It's going to be false。

 I'll tell you up。What do I have。So now suppose I have a system K。Which is consists of all the X's。

T is vector。Such that F I。Of x is greater than equal to 0。F online。

These are polynomials of degree atmost D。GJ of x is equal to 0。For。Bunch of polynomial equalalities。

 bunch of polynomial inequalities。I asked the question。Is key。我 name。Is this system。Consistent。Okay。

Now， you can go back to this， this kind of thing。You can say， well， instead of saying this max。

 I want to say this is bigger than。Some， some value see。

I want to check if the max card is more than C。😊，If it is， then this system will be consistent。😊。

If the max cut is not more than C， then the system is inconsistent。So I'm trying to ask the question。

 is Max cut at least the N hard problem。 It's O。That's the question we have。I'm asking。

 is K on empty， This， This is the example。 When you， you know， get lost， just think of this example。

Mascat。Okay。嗯呃。You know， these are， these are， yeah， these are polynomial equalityities。

 are polynomial inequalities。That's all， that's up there。I would love to say。Suppose。You know， so。

 so this is the question we are asking。 And it's the same question as Farkaash was asking up there。

Is that system A X less than equal to B is it empty。Okay， non empty， empty。 whatever。

 So there there should be two cases。Au。That exists in x， such that F of x。

Is greater than equal to0 for all I GJ of X。B equal to0 for j。

I don't know why I'm writing this down or。I would like to say negative1 is equal to。G，J of x。Dmes。嗯。

Q， or Q， the terrible。 Give me another letter。Which is not confused with anything else。啊。没。With that。

A。No， all is， you know， is vector to hell dude S J。However。Okay， no no yes。Plus。Okay。H I of x。嗯。

F I of x times some H。With the following things， these are non negative。These are unconstrained。Okay。

What do I want to say， I want to say if the system is inconsistent。

Then I should be able to prove0 is equal to negative  one。Okay。The only way you know。

 I should be able to prove this is the system is inconsistent。So I would like my， my proof system。

 my mathematics to be sort of strong enough that if this system is inconsistent。

 there is no solution here， then negative one is equal to。Something， which is。0ero or higher。Okay。

 let's look at this。GJ of x is supposed to be0， right。0ero times anything is 0。

So this part will be 0。F I of x is non negative。Non negative times。 No negative is non negative。

So this part is non negative。 This part is 0。But， this is negative。So I'm proving 0 is equal。 I mean。

 something positive is equal to something negative。The system is inconsistent。

 I should be able to prove this thing。Either this you know。

 either the system is consistent or I should be able to prove the system is inconsistent。

This would be the ideal situation。Parkahilemma prove exactly this when F's and Gs。Are linears。

But S and G are no longer。Okay。So such a statement is false。But a cousin of this statement is true。

The cousin of the statement is the fault line。I was thinking of these as unconstrained scalers。

But now there will be unconstrained polynomials。ok。I'll be。 I was thinking of these as。诶。Scals。

 positive scalers or non negative scalers。Now， there'll be。Polynomials。

But instead of being just non negative polynomials。I can tell you more。This is a sum。Of squares。Okay。

This H I of x looks something like， you know， I I'll give you an example。

 H one of x could look something like， you know，2 x 1 plus 3 x 2 plus 5 x。3 cubed。

Squared plus x1 x7 minus x 3 minus2 x 3 squared。Plus， working。Fourth power，4。

It's a sum of squares of polynom。This object can never be negative。It's always not negative， right。

So wherever we were adding in。Non negative scales we are now adding in sums of squares of polynomials。

 sum of squares S O S。系诶。So the Tem says。Okay， this also affect fake theorem。 But let me say it。

 and then I'll tell you why it's fake。The theorem should say it doesn't quite say this。

Either the system is consistent or if it is inconsistent。

 then negative1 is equal to something positive。😊，And what is positive， Well。

 it's G J of x times S J of x。This is a zero polynomial。At any point in here， this could be anything。

 It doesn't matter。 Ze kills everybody。And this was a non negative polynomial。

 It's being hit by a S O S， which is a non negative polynomial。 So these are non negative polynomial。

 sums of non negative， non negative。Negative 1 is equal to something non negative。You have a proof。

So as a proof theorist， you would say。This system is。Is， you know， it's， it's complete as well。

 either， you know， you can show that this is， the this is consistent or you can prove inconsistency。

Okay。Sad fact is this theorem is not without making additional assumptions。 I can't quite say this。

 this statement is quite true。I can tell you the real statement。 I will tell you the real statement。

 because you know， I should。啊。But I wanted you to first， just。See whether， you know。

 does this make sense in the context of farrccious lelemma。

Paarka Lama was saying I can just combine these guys using just positive scaleals。

 not negative scalers。😊，To show an inconsistency。Now， I can't Scalrs don't suffice。

 But if you multiply these by polynomials， they do suffice。So should do you think of this pluginage？

Dotly， do。是 no。So definitely a generalization focus。

Why am I telling you this in an advanced algorithms class， you'll wonder。

But it it's useful to understand the context。And the reason why， you know， I'm telling you。

Is the following。啊。And it comes down to your question。Imagine that this theorem is true。

There's some stars somewhere， some some disclaimers。Suppose。The degree of these。Eches。

The degrees of these ss were also small。Then my claim is that you can actually find this proof。

In polynomial， I mean， polynomial。 So suppose， so let me just write it down。Suppose。

 this is irrelevant。You understand what sum of squares of。Suppose。The degree。哦。

S J of H is bounded by D prime。So then we are saying negative1 is equal to you know， whatever。Then。

The RHS。His statement has degree。At most D plus D prime。 Remember， the F and Gs had degree at most D。

Okay。And then。Can。Find。Such。Bothof。In dying。And to the order。How I haven't told you， when actually。

 Ive told you， this is semi definite programming。But I haven't really told you。I'll tell you again。

 We'll come to that。O。Or is it to show。This one。Okay。

 this one is impossible to show because it's false。 but the true variant of this。 I mean。

 so either I can restrict。What case。And then， it' will become true。Or I can， you know， Ill。

 I'll change this statement and then it'll become true。 How hard is it。 It's kind of a little hard。

 I don't know。 I mean， you know， I've seen the proof， but I don't know the proof。I。

 I won't be able to teach it to you。那这个。Maybe那。After a few months。Okay。

 so the the polynomial version is almost true。 So let me tell you two ways in which it can it can be made true。

Approach 1。Suppose。K is compact。Closed and bounded。If you could show that K was compact。

Then this statement is true。Okay。Boundedness gives you some power。All it。You replace this。This。Thing。

Let me write down a statement， which is slightly more this whole thing on on speed。

Negative 1 is equal to。Summation over G J of x S J of x。As before。Plus。

Let's ask the following question。Suppose I take f1 of x， which is non negative。

 and I multiply this by f2 of x。 It is also non negative。 The answer is non negative。Okay。

So let's look at a subset of the。呃。Let's say that there's going to be L of these guys。

I is equal to1 to L。L inequality constraints。 So S is a subset of these L。

 Now you will choose an h S of x。 What's say Oh， S is a subset of L or S。D is， thank you。

I think tea is okay。So look at any subset of these Fs out there。Therell be S O S。

Polynomial for that subset。Times the product of F。I off。X， I belonging to capital D。

So it's not enough to just look at the F by themselves。

 You might have to multiply them together in order to get your。そ的是。I guess。He is。Case compact。

 but not all。K is compact， but not convex。 I think， so yes。Think so。O。Does this statement make sense。

 You know， either the， the system is consistent or you can write negative one is equal to something which is 0。

Plus。Non negative times。 product of non negatives， non negative。

The whole thing should be known negative。So if you had a solution。

This whole thing would be non negative。 This whole thing would be 0， but that would be -1 impossible。

And the theorem says this theorem that I don't know the proof for。

Says either this is true or there exists a proof like this。Okay。

No guarantees on what the degrees of these guys are。 the degrees of the Ss and hs are。

But if they happen to be low degree。Then this is starting to give you a sense of， you know。

 how much time it would take to find this proof。Well， you。

 the amount of time it would take to find these proofs。呃。You know。This， this whole thing。

Could be of degree。D to the L。And then this would be of degree from the prime。 So n to the something。

So some creative polyo。Okay。This why you're ready。啊。The sum on the right。Doesn't it evaluate。It。

 it evaluates to 0 only on the set that I care about。

Let me give you an example of what this statement is saying。Are there questions。I feel like。

 you know。Sort of。A people like completely， yeah。I realizeizes the statement for all them。

W whichhich one。This one。 So this is an equality， which is like a is's a functional equality。

So you know， yeah， So this is， this is true for all X。 Basically， the right inside will evaluate to。

Native one。嗯。Which one。So， you know， D prime is an artifact of this proof system。It's the。

Like D is part of the input。D prime just happens to be the proof I can give you that this system is inconsist。

It's not in my control。It's just mathematics。You see what I mean。O。ゆっぱい。还这些。我有个设。主的似。我要。Right。見てと。

So maybe let me say the following that each of these guys。 So maybe I should use a different color。

 I'm writing on the same thing again and again。F and G have。Degree。At most B。You know。

 this is a sort of pedantic point， but I do want to make it。

 F and G have degree at most B is a given to me。 It's part of my input。 this is like。

But the theorem is saying that there exist as an H， which have this property。

And I have no control over what S and H will be。 This is just， know。So all I'm saying is。

 if I got lucky。And S and H have low degree。 Then I'm in great shape。I mean， in fact。

 I could just say， suppose this is u most de prime。 D prime is just the output of this thing。 I mean。

 this is a fact which is true for all D prime。But really， I want to distinguish between the prime。

 which is。Coming out of the proof。And D， which is an input to the whole system。Kind of sort of okay。

So let me use this。To give you a proof。 So let me say there is a theorem。Suppose。P is the polynomial。

Which is not negative for all x。This is Hilbert， something， something problem， right，17th。

 maybe 17th。 Thank you，Right。He asked， is P of x equal to S O S or P of S belongs to S O S。

Is it always true？That a polynomial multiate polynomial。Which is nonze。

Can it always be written as a sum of squares of other polynom。We answerずれの。

But Hilbert did not know that。 Maybe he knew that。 I don't know。 Maybe I， I forget。

I forget the exact history。 It's not important。It makes better story if you didn't know it。嗯。

And there are examples that this is not， this is answer。No。Yeah。But then art ensured。

A certain theorem， which will just derive from here。Okay。So what am I asking。I am asking。

For negative P of x。Okay。This is the only。Okay， maybe let me even get to。Strict inequality。

サポージマスキンですね。So let me throw in my， let me say my K consists of all x such that negative P of x is greater than equal to 0。

哎。This is just saying， P of X。Is less than equal to 0。I'm marking this question。

Suppose P of X was actually strictly positive。Everywhere。Then the system， then what if K。Empty set。

Otherwise， K is not empty。So， I'm really asking。K龙。So I've defined K， K。 let me define it。 that way。

 I'm asking question。P fact。嘅。😊，Is empty。啊。K， then T implies。This， right。

B of x is strictly greater and0 for。Right。If and only。

I just want to figure out whether the case is empty。Okay。But we know as way of， you know。

 what happens if K is empty。Negative1 is equal to0 over negative 1 is equal to this garbage， right。

So let's write down the garbage。 Ne one is equal to what。There are no equality constraints out here。

This portion just goes away。What sets can T be。What's that it can be two。 It can be a empty set。

So I'm going to say this is edge of the empty set。Times the constraint that you know。

1 is greater and equal to 0， really。Plus。At。Corresding to P。没 forget H of X。Times。医疗费。So。

 it's negative P of effects。My axiom was negative B。Is greater than equal to 0。Right。😊。

You are happy with this。 It is just like a。Mechanically， I'm doing this。 I'm just saying， look。

 there are no terms here。The only terms are h of the empty set times a product over the empty set。

 which is one。An edge of the set， consisting of P。Thanks， negative。Because that was my axom。

Let me just move this step。Let's write this thing down。Let's move negative one to the right hand。

 So I get edge of the empty set of x plus one。Is equal to。H of x times P of x。So far is good。

So we are saying P of X。Is a sum of squares of polynomials。Plus， a sum of squares of polynomials。

1 is， you know， it's one squared。Divided by a sum of squares of polynomial。

It's a rational function of sum of squares。Which belongs to， you know。

 I I'll abuse notation and write it as S， O S divided by S， O S。This was a theorem of Em Rtan。

In the year， something， something Who knows， Who cares。Our time proved Art。 I don't know。 always。

 we had， we learned algebra from a book by his son。啊。

And so we always called it art And It always sounds wrong to me to say art even though that's his real name。

 right， tell anyways。He proved that a positive polynomial can be written as a rational function。😊。

The ratio of sum sub squared。对。It's coming out of this sort of beautiful theory。

And the algebraic geoomes do this for a living。Why are we interested in it Because we are hoping。

That， you know， these kind of statements have。Proofs of low degree。And then， we'll find them。

Where are these coming from， So in order to do this， let's take a two break。 So this is one story。

 This is coming。 This is coming from Farca dilemma。Is basically saying， look。

 I'll give you a system of polynomials。 I want to figure out whether it's empty or not。If it's empty。

 there exists proof like this。If it's not empty， there exists a solution。And really， this is。

 you should think of this as duality。😊，Which is the hidden， you know， hero behind the。

Hidden here and behind the whole thing。It's， it's making everything tick。 So this is really。

 in some sense， duality。 I'll try to make this more formal in the next part。

 We'll see how far we'll go。But。O。Let's do it。Next up。这是问。O。Let's。We back。Okay， so if。There is a lot。

 but you know， you' you ain't seen nothing yet。This this really keep going。I， I mean。

 this stuff is beautiful。 It's， it's just amazing。😊，So let me tell you a little more。Okay。

So piece1 was this sort of duality out there or this theorem of alternatives， if you wish。

Either a system is consistent in which case there is a solution or it is inconsistent and you have proof like this。

😊，How do you find these semi defite programs？ I haven't told you how to do it。

But sum of squares will have to play around。So let me give you ingredient too。

I give you a polynomial P of x。And I ask you。Is this polynomial a sum of squares？I'm not saying。

 you know， is it not negative and， you know。And hence， you know， whatever art here。 I'm no， no no。

 I'm just saying。I'm asking you to solve this problem。 Is this P of x sum of squares。

And my claim is that if you can solve semi defite programs， then you can solve this problem。

So remember what what this means， Im asking， does there exist， does there exist。

Some polynomial Q of x。 remember， multivariate polynomial such that p of x is equal or So maybe let's say Q I of x。

Q1 of x， Q2 of x， etc cetera。Such that P of x is the sum of Q， I of x。すこい。Okay。

So I'm taking each polynomial， squaring it， and then summing them up。I'm asking you。

 is P of this form。This is the problem I want to solve。And the answer is， you know， So sort theorem。

Soivable。By。S me defite programs。TheQ。No restriction on the key。Right， so so this P has， let's say。

 degree。Atmost day。You can convince yourself that these Q Is。

Will have at most the degree of Q I must be at most D over。

Because you're going to take them and you're going to square them。That's one double degree。

And none of these， you know， there is a little argument to we make that look you can't just you know things can't just cancel out。

 you can't just say well start off with likeco degree。😊，And somehow miraculously。

 all the high degree terms will cancel out。 It's not going to cancel out。But that requires the proof。

 And we， we can do this offline， Piazza。So if you gave me a degree D polynomial。

 then I can do then I can guarantee you that those Q I will be of low degree。

 low degree D over 2 okay。And then， the run time。As you will see， will be at most end to the order。

이걸。So by SDP。Why。So， suppose。B your thanks。Is equal to Q of x。Square just， you know。

 it the square of a polynomial。Just for the moment。So what is Q of x？嗯。

Let me just introduce some notation out here。 By now， you guys are used to me whenever I'm writing x。

 it's really x vector。 It's a multivariate polynomial， right。Now。

 I'm going to start saying x to the alpha， where alpha itself is a vector。

And this is just x1 to the alpha 1， x2 to the alpha 2。X， N to the alpha。Okay。Alpha the integers。

 So alpha belongs to。Z。Great。0。그是。Not。it's like a component was。What's that it's not。SoYeah， yeah。

 it's， it's the， it's this。 So， so for instance， x1 x 22， the 2，3 is just x 1 squared x 2 cubed。

 This is a monomium。This is， yeah。本人呢？So I'm just writing x to the alpha。Makes my life easier。

So Q of x is equal to sum over every possible choice of degrees of the x's。Times x to the alpha。Okay。

Where alpha belongs to the integers， non negative integers。And tus of that。And the。

L 1 norm of alpha is at most。 let's say， B over2 or something。

This is just saying the degree that most d over。 the sum of exponents of the x' is can't be more than d over。

You know what Ill I'll get tired of writing。네啲。話。We O。changed nothing。O。哦。Square。G square。

So what is this。This is sum over alpha and beta of this with these constraints x to the alpha。

X to the beta。Oh， sorry。C， alpha， C beta x to the alpha plus。Nothing's happened， right？Now。Think of。

You know， what are these。What are these Cs， these are just scalrs， right？😊，Because， you know。

 this is a polynomial。So the coefficients are scaleals from the underlying field。

Which I always assume is the realful time。So， this C alpha。Are just scalers。

So I can write a vector C。Which is C of the。0，0。Let's say two variables， just for the moment。C of 0。

0， C of。0，1， C of 1，0， C of 1，1。This just corresponds to C of the， you know， yeah， whatever。Amount 1。

 C of x 2， C of x 1， C of x 1， x 2。1万支付了。Remember， these alphas correspond to exponents， right。

So I'm just writing down the polynomials that correspond to these。

 the mononoials that correspond to these。And this thing。Is equal to C vector。Transpose。

So some sum matrix M。Times C greater。You know， this this like this is X alpha， you know， X， I。

 X J times some quantity， I J。This is getting too abstract。 Let's do an example。For once。

 I was prepared。I want to check whether this polynomial is SOOS。😊。



![](img/50af49263d6970da6f9ad8b0b03462e1_3.png)

For now， let's just imagine that this polynomial was， yeah， so so whats what's happening。What's that。

But I' need export more。Or x 4。 Yeah， I think it's x 4 x 2 to the4。 There is no。And actually。

 this tells me I I'm Im I， I'm doing something fishy out here。 let's let's come back to this。

 Maybe I won't do this， but we'll see。 Maybe the seas are。Yeah，''m。Forgere。Let's do it by example。I。

 I'll， I'll correct myself。I have this polynomial。 I want to check whether it's S O S or not。

 Here's what I'm going to do。I want to say， well， this polynomial。



![](img/50af49263d6970da6f9ad8b0b03462e1_5.png)

Im going to write in the following way。Okay， so actually。Let me， let me come back to this。

 I'm switching between the two things because I goofed up。Let me define a matrix。

 Let me not define all vector out here。 Let me define a matrix。This matrix。Has entries。Which are。

Index， so， so this matrix is indexed by vectors， alpha and beta。Okay。And what's the entry in here。

It's C alpha C beta。Okay。This matrix is indexed by all possible alphas which satisfied this。😊。

There are end to the。D of these things。我这。And。And this entry。What can you tell me about this matrix。

It's symmetric。It's。Positive semidefinite。It rank one。And you know， this。

 this matrix is equal to whatever the previous vector had written down C transpose。😊，It's rank。

Which is positive， semi definitely。Okay。系。And now。What I could do。Is I could say。This is。呃呃呃。嗯。

A thing consisting of x's。 These are all x to the alphas。 You know， x x to the alpha 1。

 x to the alpha 2， all the way to x to the。Calpha， whatever。 However many alphas there are。

Transpose C。X to the alpha1。Next to the alpha。This is this expression out here。

And this is getting abstract。 So let's write it down。I want this polynomial。都 equal。

There are going to be some numbers out here， which I don't know。

I want these numbers to be such that if I multiply this thing out。I get this answer。

What should the number here be？0ero， because I want a constant term。 There's no constant term here。

That on the right。あ、です。You w to write it。This way，1， x 1， x 2。X1 squared， x 2 squared， x 1， x2。Yeah。

Okay。Is there a term corresponding to x1 no。The answer here should be there on。In fact。The answer。

Corresponding to all these guys， the only thing that's going to happen is there's going to be a 3 by3 matrix here that's going to matter。

Okay。Why is this because x2 times x1 squared corresponds to x1 squared x2。

 which is not present out here。Whats that。This corner is2。Good。How about here？4 by。By 4 by 4。

'm X sorry， it's not X。Just to be clear， you。You rule到 that呀。Just begin with a degree。

Because of the degrees and because those terms did not。 Yeah exactly。 I mean。

 the just degrees were enough to rule it out。Good。嗯。Negative half。2次。Negative half。Why。

 let's just be clear。X1 squared， x2 squared。Ha a coefficient of negative one。

 but that should be dis distributed evenly amongst its two。It's a symmetric matrix， right。

How about here？X1， x2 times x1 squared。X 1， x 2 times x1 squared，1，1。Should be two。Thatはい。Miills，5。

0ero。没有我。你看看那个关了。How is this negative one。The the third term。Third terms。No， what's happening out。

 TJ， sorry。I am a little confused。I think that it was right。Negative  one。Sn to be。😔，The third term。

So there's something which is bothering me。😔，Exactly， the x1 squared times x2 squared。

 It can come from x 1 squared times x 2 squared。😊，X 2 squared times x1 squared。And X 1， x 2 times X1。

 x 2。Right。So there are some of these entries， which I'm not sure we can which ones I don't even remember。

 which ones。我 like we keep running。No， I want to。呃。Do this a little more carefully。

So x1 squared times x1 squared is x1 to the4。 That's 2。呃。Okay。So， x 1， x 2。Times x 1， x2。

 Let's call this equal to。So， so here， here are the constraints I'm gonna to write now。 This is。

 this is a matrix， right。This matrix is positive， semi differentite。This is what I want for sure。

 right。What else do I want。I want this entry。To correspond to the coefficient of x 1 to the4。

I want this entry to correspond to the coefficient of x 2 to the 4。I want。This entry， I'll call this。

嗯嗯。B嗯。Plus。This entry， Q plus this entry R。I want that to sum to negative one。This entry。X 1。

Cubed x 2。Is there some other way of getting x1 cubed x 2。Now。

 I think these are the only two ways of getting x1 cubed x2。So x1 cubed x 2。

 this should be one and one。Because they should give me this。

These two entries should give me x1 times x2 cubed。Which is0 out here。So these can be， I think， zero。

Okay。So I'm asking for the question， is there a matrix which is non negative。

 which is positive semi definite。And have I made a mistake。あのそ急なスピて。Q has to be equal to R。

 So I call this R。Now I'm asking P plus R plus R。Is there a setting of P and R's。

So that this matrix is positive， semi deffinite。Yeah。Which one。ですけ？Oh， that's I didn't drop it。

 I don't know why， you know， I should call it S。But what should S be。Oh there should be two， right。

方案可。一些产就是。This one。You were highlighting。I don't know what I'm doing guys。Okay， I think this is fine。

This is， this two is coming from there。 This find is coming from there。

These zero are coming because those terms are missing。

 Those that one on one is coming because of this too。

And this P and this R and this R have to sum up to negative 1。Okay。If this guy were positive。

 semi different。Then it would give me back a polynomial。Which looks like that。

And you can convince yourself that it goes both ways。

That if they were a polynomial which was you know whose square was this quantity。

 then it would be writeable like。😊，And since P S D S is closed under sums， under positive sums。

And sums of squares are closed under sums， by definition， positive sums。The fact that this is rank 1。

 we can't enforce it， but we don't need to enforce it。Because it's a rank one matrix。 I mean。

 it's the rank one matrix。 if it's a sum of one square。If it's a sum of many squares。

 then those rank1 matrices will all add up to give a high rank matrix。It's not important。

the Tem says。When the。Checking。Okay。B belongs to SOS S。Can be done。呃。oh， so this is degree D。

Can be done by SB P。Off size。At most。And to the day times n。That kind of thing。Just take your matrix。

 Just write it down。And then every coefficient， a coefficient like this will come from perhaps many different entries in that。

 That's a linear constraint。You'll have a bunch of linear constraints， and you'll have one1 P S D S。

 You'll say， is there a setting of these。Linear constraints。 know。

 the linear constraint here was 2 R plus P is equal to negative 1。

And yeah I had some notes which show you how to solve this。You know， basically。

 all I did was I took this sucker， and I threw this at from Alpha。 And I think it gave me the answer。

And it gave me a decomposition of this inter sum of squares。 And its a miracle。Good。

So at least this gives you a sense， hopefully。Go ahead， Kegan。Please。上な先生。啊，嗯。この that。Exactly， so。

 oh， I'm not going to tell you how to solve this。 You， you just inherit the method of solving SP。

That's done。But the important thing I wanted to tell you was you can check whether whether。

Whether a polynomial。I the S， O S。Why do I care about this？Because remember。

I want to actually solve things out here where the objects Im finding are S， O S。

So I need to somehow optimize over the space of all S O S polynom。

If I can't even tell you whether polynomial is S O S， I sure as hell cant optimize over that space。😊。

So at least I've got step one。I know how to optimize。

 I know how to check whether a polynomial vessel。When comes to the hard part。

 How do you optimize over that space。But。I think we' are running out of time， anyways。So啊。Probably。

 I'm not going to be able to give you complete punchline。But I can't talk for 10 minutes。

There's never a shortage of things we talk about。So far so good。 bless you。So far， okay。

Polynomial in S O S， you should be at least more or less convinced of that fact that you can check S O S S。

 we， we've struggled through this one。I find this very useful， Just struggling through this。

 And you realize， oh， I can't just write down the numbers here。 This is too simple。

And need to actually solve some linear qualities， subject to positive semi。

That's why you need SDP and not just checking whether something is P SD。Okay， good。So， last piece。

So this last piece is going to be very， you know as if actually the first two pieces were the first piece was I gave you a bunch of theorems。

 I didn't prove them， but at least I told you that they were theorems the second piece was fairly constructive the third piece is going to be completely impressionistic。

😊，你就新啊。That's a。Watch the little birdie fly， that kind of thing。So here's what I want to do。So this。

 this3 is okay， So youve seen S O S is in SDP。 you've seen Farash lemma leading to that that theorem。

😊，By the way， that theorem has a name to it。 It's called positive stzas。Maybe I'll write it down。

 I'm not going to bring that guy down positive。it's not Sta。Soander， hows a German？不程。Whats say。

 yeah， you right now。So I think it's it's zs， I think， means in a statement or something like this。

 And this is like。Is that do you know German enough Oh Okay， okay。

 and I think this is like a theorem about positive things or something like this。

It there was a precursor to this called null Sta inzas。Which is the theorem of about zeros。好的。

What's that。So he's got a combinatorial version of the nulestelza。😊。

So that that theorem was called the positive challenge arts， often because it's bit of a mouthful。

 People just call it pi arts。😊，And， of course， the S is pronounced Z and the Z is pronounced S。

 So you know， go figure。😊，So that's the extent of my German。嗯。But， okay。Good。

So those were the two pieces out there。 And I'm going to give you the third okay。

I'll shut up and just tell you the stuff。What do I want to do。I want to minimize the polynomial。Over。

F I of x is greater than equal to 0。G，J of X。Is equal to 0 for all J。For all I， hence。

 let's just call it K。Okay， I wan to solve that problem。It's N hard。Trick。

Whenever you have a problem like this。You can。Relax it。 You can contextify it。You can say， look。

 I'm not looking for a particular X out here。I'm looking for a distribution。Okay。So。

 mu is distribution。Over。Pro distribution。Over K。And I want to figure out。What the expected value？哦。

P of xs。Where x is drawn from this distribution。Okay。Giving a distribution over every point in care。

And now I'm looking at the X drawn from this distribution。And I want to minimize this object。

So really the right thing to do is to take the point distribution on the minimizer。

Or any distribution just supported on the minimizer set。That will minimize this expression。

But why did we do this， Because， you know， now everything is convex， like your muse or distributions。

 right。For those of you who do approximation algorithms。

 this is like taking the fractional relaxation。😊，The fluid relaxation， if you will。Okay。

 but this beast is enormous， right， I mean， I'm writing down a distribution for all of K。

If case continuous even the line line interval， I I'm dead。Okay。

So I don't want to deal with this as such。 I want to。So here's what I want to do。

I care only about the expectation。And P is a polynomial。It's not a general function。

 So I want to use some properties of polynomials。Here's one property of polynomial。

 I know properties of polynomial。 I know P is of polynomial of degree。Atmost B。So P has a basis。

The bases are all mononoials。Of the form x to the alpha， where x and alpha are both vectors。

Where the alpha sums up to at most。 Okay， who's。That's okay。I know what's happening。

 I'm not out of that。These。For all alpha and z to the n。Alpha。

 the one norm of this or Z plus to the N。 Al1 norm of this is that mostly。 this is a basis。

So I don't care about the value of this distribution completely。

 I only access it where its expectation on a polynomial。So suppose I could write down。

 So I could say， suppose the expectation of a polynomial of x to the alpha。Is some value。

Let me call it L of x to the F。This， this， it's， it's some scalealr。

These will be the unknowns of my system。For all love。If I know these values。

 then I can evaluate it on any polynomial by linearity。L is a linear map。Okay。

I should ground one the expectation， I mean， basically L of one should be one。

 The expectation of one。 If I plug in one out here， I should get one out here。Okay， so really。

 this is a special case of this。😊，Okay。And then I want to say this。L of x to the alpha。Agrees with。

Expectation。 So basically， I want to hear what I want to do， right。嗯。

Agrevees with the expectation of X2 B。This is what Id written earlier， Im just writing it down。

For our alpha， and I want to minimize。L of P of alpha。Which by linearity。

Is just a summation over whatever C alpha， which belongs to P。

The objects that I'm looking for are these L。And I'm looking for the values of these Ls。

For each of these mono。I'm looking for n to the alpha N to the D many objects。

I'm looking for the value of what is L of1， L of X， X 1， L of x 1， cubed， x2， eta。Okay。

But then I have this annoying constraint。L agrees with。The expectation。

We have to ground it somewhere， right， Otherwise， I can just cook up any numbers I want。

What is my guarantee that these expectations that we are taking。Satisfy these properties。Good。

Two more minutes。 I'll shut up after I。So what you end up doing is you say， oh。

 L will be a linear map。 We want to minimize this object。 L of1 is one。

But I'm going to write down a few more constraints。I'm going to say。That L。off。My input， G J。

Must be equal to 0， because hey。GJ is equal to 0。 So the expectation of that should be equal to 0。

Right。But。L of GJ。Of x， right。Times S J of x should be equal to 0， as well。But any estimate。

So we're going to throw in these constraints。For all low degree estate。In fact， in this case。

 we don't even probably don't even need much control over No， we need。

 we do need control over the decrease， I think。Similarly， I'm going to say L of F。Ie。Is not negative。

This will give me inequality constraints。And similarly， I can write down L of F I times H I。

 where H I is the sum of squares is going to be non negative for all H I am belonging to sums of squares。

And I'm I said， impressionistic。 you know， this is the definition of impressionistic。Basically。

 I'm saying， look， I'm going to tell you the value of each of these moments。

This is often called method of you know， one of these method of moment type things。

I'm looking at the expectation。 L is really the expectation operator。

I am looking at the expectation of this quantity under some unknown distribution。

But this expectation operator has to satisfy some constraints。

And I'm going to throw in some set of constraints。 and I'm going to try to minimize this quantity。

If I could throw in constraints for all。呃。Polynomial H and S out here。

 I would get back the positive st that。I can't。So I'll throw in the constraints corresponding to low degree。

S is and matchesches。That's what we wanted to find。So if I had， you know， maybe one more lecture。

 what we would do if we would write this thing down。

We would see it's a positive It's a semi defite program。We can solve it。

And then the second thing we would do is we would take that semidefinite program and take its do。

And the dual would be exactly statements like that。

So really what that often this is known as the pseudo expectation view of sum sub squares。😊。

It's just saying， look， there's this expectation I want to get。 I can't get hold of it。

I'm just looking at this expectation。From the perspective of low degree moments。And that gives me。嗯。

An approach which I can solve using S Ps。And the dual perspective is the perspective of the positive challenges。

Let me shut up there。So that's， you know， it gives you a high level idea of where。

 where all these pieces are fitting in。😊，You know， I can point you to more references and we can talk more。

 I'm happy to talk。😊，But that's， that's the quick view of S， O， S。Pve Qari， you know。

 I mentioned this at the beginning。 I'll mention this again。 Pravsh has the entire course on S O S。

So if you're interested， he's got the videos online。 This was from the， you know。

 early days of the pandemic we were putting。 Yeah， we were， yeah， all our videos are online。 I mean。

 that's one great thing that's come out of the pandemic， right。😊，We。

 we've got over our hesitation of putting our lecture videos online。 We are like， hey， what the he。嗯。

Good。So， on Wednesday。嗯。Will do。Another one of the requests， which is。

Concent Martiningale concentration。And then next Monday， we will do。

 well touch upon high dimensional expanders a little bit。And talk about how to sample。啊。

How to sample random spanning trees。For lack of a better。Good， thank you guys。

