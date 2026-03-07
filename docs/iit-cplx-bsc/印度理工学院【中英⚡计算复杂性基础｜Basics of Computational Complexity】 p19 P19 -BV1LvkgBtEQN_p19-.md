# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p19 P19 -BV1LvkgBtEQN_p19-

![](img/628aa2817a733bbcef82232b1bcc8b0a_0.png)

So， last time。V。Began this topic on space complexity。So， we defined。Non deterministic version。

Of space， right， So basically measuring the space。Resources in a non deterministic Ting machine in N DTM。

So based on that n space for a function F can be defined。

Basically N DTM that decides problems which can be solved by an NDTM。In。Around F of N space。

And based on that， we define， we can define NP space。

Great union of end space for all polynomials and to the sea。P space will be the version。嗯。

Which is deterministic。Duringuring machines or union space of into the sea。

It's obviously a subset of and peace space。Then， there are these。Classes for very small functions。

Okay， login， for example。Anything less than login will not be of much interest。To us。

But login is interesting because you can at least index the。Input string。

Input string has length end so just to index a position， you need login bits。

So if the work tape has this much。Then， we say classes。

The problems which can be solved is lock space。And the nonomistic version is Nl。W， for example。

 addition multiplication you can do。In this space。P and and P become equal under P space or Ra。Okay。

 you can show this。And you can compare D time with space with n space and with exponential time。Okay。

 so let us now look at the notion of P space completeness motivated from N completeness。

But now we are talking about polymial space in the workta right so that' is a lot of space。And time。

Is actually potentially exponential time。So hence， a lot more problems you should be able to solve。

In peace space。So what is the hardest problem that you can solve？So， this will be a potentially。

AHarest problem in P space。 It's called T Q B F。O， Tq Bf is quantified boolean formulas that are true。

Through quantified bulloleing formula。So here we have many quantifiers， there exist for all。

 there exist for all， this  Q1 x1 Q2 x2 dot dot Qn xN。All the variables are quantified。And inside。

Inside most part this pooling formula  phi1 x。Right， just like。You had in S。So， the sat is。

At the core of this definition。So you can think of phi also as a CF。

But we are just calling it a Boolean formula we are not talking about what form it is。

 but cF is also fine。And this formula should be。主hu。Right， so Q n dot dot  Q n。On5 should be true。

So the first thing that we observe。The easy part is that T Q BF is in peace space。Okay。

 you can solve T QBF in polynomial space。Now， look at the。

Domain of x12 x and it is 01 to the n rate that exponentially that is exponentially large。So。What。

 I mean， this brute force。Algorithm has to be implemented very carefully。

If you want to do it in polynomial space。So， let。Saai。Q，1 to Q， N。5hi x。Be a QB F。With size M。

Size of fire being。M。So just think of the keys where they exist for all alternate。

So you have to first check there exist N X1。Which is possibility01， then you have to do for all x2。

That is both the possibilities，0 and 1。Right again， there exist x 3， which is the possibility 0 or 1。

 So how do you do this They exist for all together。Right， thats。嗯。

That is the algorithm you want to implement。In polyial space。It's a polynom in n。 How do you do that？

So， we will do it recursively。 Okay we will fix x1 and then we will go to x2 and so on。So， we check。

Size。Zhu。😔，Bai。Or recursible algorithm。So in this recursible algorithm。It is based on this idea。

That size is true。If and only leave。In case Q1 is their exist。Then， you want to。Q，2， x，2， dot， dot Q。

 and X， N。5hi with x1 set to 0。N X2 to x free。You want either this。Or。5，8 x 1，1。

So in the case of they exist。One of these should be true。

 either x one equal to 0 should be true or x1 equal to1。 setting should be true。So， that's one case。

The other cases。Q1 is。For all。So， then what you will want is。You will wantt。

So let me change the colour of this。The cun is for all， then you want。Q 2 x 2。Qan X n。0， x 2，2， x， N。

Both of them， write x1 equal to 0 and x1 equal to 1。Okay， so there are these two。

Possibilities case 1 is Q1 is there exist。 Case 2 is Q1 is for all。And we have。

These obvious conditions， the only difference being R and and operator。So。

 you check whether Q1 is there suppose  Q1 turns out to be there exist on the check then you are in the first case。

And。You basically have to。Do both of these， right？You cannot do them simultaneously。

 you cannot do them in parallel， so you actually do it sequentially you first。

Make the check of x1 equal to 0。Then you reuse the space and do the check off。I mean。

 delete everything from the work tape and to the check of x1 equal to 1。In the same space right。

 so the space is used only once。And once you have done both these sequentially。

 you can easily check the answers， whether it is an or or an an。That will not cost anything。So。

 with this。Subay。Reusing work tape。Space。嗯。The space complexity is。Space complexity。S， N， comma， N。

Is given by。So S N comma M。Which is we give a recurrence where n is the number of variables that is reducing。

With every recursive call。And m is the size of5， which also reduces because you are setting。呃。

The previous， let's say， x variable， x1， x2， whatever it was to 0，1。So an upper bound on n comm M is。

That you reduce and to buy one。Right。Even in the worst case。

 this is happening when you do a recursive call n falls。

And the extra space you need to do this recursive call。Is as much as the size of the formula， right。

 which is。M。So we go of him。 So that's the recur， which will give you。That S of Na M。

Is equal to so this m gets added n times。N callss write order N M。Which clearly means that。

This problem of P Q Bf has been solved in peace space。Right。

 so let me give you an exercise to improve this。So improve this to order n plus m。

Okay don't be satisfied with the quadratic growths， make it linear n plus。But either way。

 this will not change the fact that。Or this will not improve lemma 1 Lemma 1 remains the same that T U Bf。

We have shown in peace space。And now comes the main lemma， which is about completeness。

Right there for every language and piece space。You can reduce it to TQ Bf。

And note that the reduction is。Deterministic polynomial time。 Okay， it's not a piece space。I mean。

 it's weaker than a piece space reduction。Actually。

 the time is also limited it is only polynomial time。

So any problem in P space you can reduce in polynomial time to P Q BF， So hence。

Once we have shown this， you would know that TQBF is the hardest problem in P space。

And it must be really hard。 It's actually much harder than。嗯。NP complete problems。Right。

 because you this here， we actually are not limited time。We have only limited space， so that's a。

ABig relaxation。So you can solve many more problems in peace space。Potentially， so let。Mbn。

Esence space during machine。Deciding ill。Good this L in P space lets。

Let this be decided by a tuuring machine M。In this much space， some function of n。Idea is。

Construct Q B F。Cai。😔，For this Turing machine M and some inputex x of length n。Of size。S of n square。

Whose true depends on。A accepting x。Okay， so this QBF that we will construct。It will not be too big。

And its truth will。Whether it's true or false， this will exactly depend on whether M accepts sex or reject。

Okay， the output of m on x。So this will be a reduction。

 This will immediately tell you that L reduces to。T Q B F。So how do you do this？Well。

 you don't have any other option except simulating each and every step of the tuuring machine name。

Right， and you have seen this。嗯。The details in cook Le reduction。So， let's just repeat that。

Subby cook。Lvin。😔，Reduction。We have a formula。5hi on M X， C prime。Of size， order of S。That is true。

If leave。C2 C， prime。Its a valid transition。Vald transition step。Of configurations。Of M X。Right。

 so this is what。You have to recall， go back to that proof and recall。

 how did we convert a transition from configuration C to C prime for tuuring machine name？

Which takes space as often。So there we are talking about time in the in cookla improve。

 but the time actually we just。Related that with space and it was really a space which decided configuration。

Right， so here。嗯。Yeah， that space will directly appear。So big go office。

Is what it is which to one step of the transition is captured and then。You repeat this。Du。

Cover the whole computation from start to stop。So， M on input。So let me make it an observation。Sim。

On inputex。Size of X to be n。Ganhe。At most， how many configurations so。At most two ways to order is。

P D sum constant。Can have。At most， these many。Distinct configurations。For constant D。Why is this？

Well， because the work tape has only space。Or of face。

And so configuration basically depends on the work tape。Space。The workspace， and。

Number of configurations then that the number of C that you can get configuration C。

 you can think of it as a binary。String。And。How many binary strings are there to race to？え。Okay。

 and we keep D to。Cover the blue up。So it is2 is 2 d times s that is the number of distinct configurations。

Configurations cannot repeat， because。Going to the same configuration would mean that there is a。

cycle。There is a loop now in the computation。Now the if there is a loop， then the it will never stop。

 the Teaing machine will not stop or I mean you can eliminate the loop。So。

 if you look at the minimum computation path， then there are no loops so distinct configurations。

So there can be at most tourist to D times as many steps right So this means that。M has。

Number of steps。Less than equal to this。Right that's the bottom line。Okay。

 there is the time complexity。 So now let us look at many steps， how to convert it into a formula。

Just like what we didn't cook levin。So， it's possible， too。We design。Q B F Sai I。C2 c prime。

That captures。Whether。C to C prime。The C2 c prime。Is reachable。In atmost， tourist to eye。Sts。Okay。

 so with input X， when M runs。From configuration C。嗯。

Can it reach tourist sea prime in tourist to transition steps。So this we can write。As follows。

So say I C2 C prime。There exist a C prime prime， which is right in the middle。Right。

 so C to C prime prime and then C prime prime to C prime。These are the two。But。

Which we have broken in a recursive way。And。So， we have done it recursively。Okay。

 so recursively we can write psi I in terms of psi minus1 because we can have。

Now this is a clever idea， it is a very computer s C idea to break the problem in equal hubs。

And we are doing it because the number of parts and number of or the time complexity is exponential right was two is to as often。

So to handle exponential， we want to。嗯。Divide into half equal halves because havinglving can be done then at most S of n times only。

So we have a chance of getting。呃。A much faster analysis， a better analysis。But does this succeed。

 So here， the problem is that this recursive。Expression is doubling the size of the formula。

Right because it take it is taking two copies of si minus1。

 so every step it is actually doubling the size。So if we keep doing this。Then。With all these， Ie。

Recurrences。The size will blow by tourist to。 So this is not good by itself。Okay。

 so this idea doesn't work。So， it gives。As a Q B F。si m commma X。As。

The configuration that starts with x input x。And the configuration that accepts sex。Right。

 so these configurations， these two configurations。Time complexity， you know。

 number of steps you know， is tourist to DS SN and you do this recursively the previous recursive。

The recurnce formula， you keep applying it。And that will give you。Start to stop。In fact。

 start to accept state。RightBut every time we are introducing a new quantifier a new variable c prime prime and this and operator which is doubling the size。

That is a problem。Butt。😔，Size of M X is greater than。Tourist to DS SN。So how do we improve this。

Why do you want to improve。Well， because the lemma view wanted the idea was to construct a formula of size only polynomial in a of。

 in fact as of square。RightBut what this idea is constructing the recurrence idea。

This is constructing formula of size more than two to s， and that is exponential。

Exponentially bad right How do you improve this？So。

 I gave this bad idea because actually this bad idea can be converted。

With a simple modification into something。Exponentially better。Okay， so what you do。

You avoid the doubling of size。How how is that possible so that will be possible by using quantifiers。

So use the for all quantifier better。 That's the idea。To avoid doubling。Okay， so let's do that。

 So let's。Reefine。Si I C to C prime。As。So there should exist on midpoint that c prime prime as before。

But then we want we will now use for all quantifier to you。

Say both the both about the first half and the second half。Simultaneously。Without doubling the space。

Without doubling the formula size。 So for all D1 and for all D2。So D1 equal to C and。

D2 equal to C prime prime。That's referring to the first half。Or。D1 equal to C prime prime and。

D2 equal to C prime。So， either of these。Two situations。 So first half。Or second half。Should mean。

That D1 to D2。Is reachable in half the number of steps。Okay， so in we have been able to。Compress。

First half， second half into just one statement。which is by using this d1 d2 new variables。

So this is the clever part。Right， and we have used。For all quantification for this。

So that we can make a statement。About both the halves without doubling the size of the formula。

 So now we get。That the size ofsi， this new definition。This is。

So how many times will this recurrence run that。D times S。Because the number of eyes is。

Or I is at most D time S， right？So that is the number of recursive calls and in each recursive calls。

 how much are we adding？To the formula。 So we are adding。Abovesi I -1。

 we are adding this D1 d2 c prime prime C prime and c。Those sizes。 So they were of size。The space。

 which is big office。It's only that much。So this is big of SN square。So in the end。

 the formula is only quadratic in the space and the other property。You should observe this。

That M except accept X。If an on leave。This T Q B F is true。Why is that well。

 Because that is what it expresses。Ultimately， the smX formula is expressing that there is a start with x and there is an acceptex。

But from。C start configuration2 C except configuration on x。So if there is a path。

 then the formula will be。Se will be true。And if there is no part。Then the formula cannot be true。

Right， because it's actually tracking the。Configurations looking at the midpoint that was the trick。

 So this means。That L has been reduced， too。Bq beeff。Right， so that finishes the proof of lemma。Do。

We have reduced any P space problem to TQBF。So， now。Lmas。1，2，2， proof。That。So what to them by。Meyer。

😔，And stockmare。It's a very old。Theorem from 1972， the TQBF is P space complete。Okay。

 so compare this with。SAT satAT is NP complete Tq Bf is P space complete and yeah so intuitively this should mean that Tq Bf is much harder。

Okay， this。This also means， just trivially。It also means that。Q， Q， B F N hard。Okay。

 when every problem in P space reduces to it， so also NP problems reduce to it， so NN is in P space。

So， TQ Bf is NP hard but。This is much harder than NP problems。

 It's outside NP these this is our conjecture。Okay。🎼，🎼。



![](img/628aa2817a733bbcef82232b1bcc8b0a_2.png)