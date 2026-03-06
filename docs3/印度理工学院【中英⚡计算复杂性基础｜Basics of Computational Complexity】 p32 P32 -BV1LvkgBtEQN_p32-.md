# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p32 P32 -BV1LvkgBtEQN_p32-

![](img/5ad536adfd421f3888b2e23e5438be27_0.png)

So now let us calculate these two probabilities。So this one is first is probability that。B。😔。

X prime minus6 is 0。L given V x is minus B。That's the same event because once B x is minus v。

You can replace minus B by Bx and then subtract and get。This equality to 0。

And probability that B X is minus B this we have calculated before， right。

 This is the this we have calculated as two is to minus k。Now in the in this first probability。

 this B x minus b is not playing any role anymore。Right， because x prime is。Different variable。

So we can as well write this to be probability of the event。😔，That x prime B X prime minus- x is 0。

That's the same probability。Which， again， is two is 2 minus k， So you get two is 2 minus2 k。Okay。

 Iclaimed。That's the idea。That's the， in fact， the detailed proof。

And moving on to the third property， which is the most relevant to our application。

 this will come from the top two。Okay， so let consider the random variable。In。Will define n to B。

The number of。Exesiness。Which under the。Random hash function。Vanish。Go to the zero bucket。Okay。

 so this is a random variable because it's it we are counting。

Thisiscount will actually depend on the random。Johoice of the hash function。Okay。

 so we S age changes。This number n may also change。Or wheel change。So， what we are interested in is。

When is this number 0， when is it1 and when is it more than1 those are the events out of which we are interested in when is it  one。

 what is the probability。So。Let's calculate that。So by inclusion， exclusion principle。We can write。

That probability。So we will calculate n greater than equal to 1 greater than equal to 2。

 then we can take the difference。Okay， so。That's what we will do。We calculate。

The probability that n is greater than equal to1 and。N is greater than equal to 2。Okay。

 these two probabilities。We will calculate and then the difference will give us when is it1。

What is the probability that N is one。So let's implement that idea probability that n is at least one this is by inclusion exclusion principle。

嗯。G over all the X's。InIn this。Probability that for random H hash function。X vanishes。

But when we do this sum， we are over counting。In the cases， when each is。

Mapping x and S explaining both both of them to0。Right， so in that event， we are counting。

In h x equal to 0， but also in h x prime equal to 0， so we subtract。

That to remove the double counting。So x less than x prime minus。Probability。The Etics。Is it extreme。

Is 0。Okay， but now when we subtract， we are under counting because we have。呃。Also。

 we have subtracted this x x prime and x prime prime。Right that we have subtracted too many times。

 So anyways we the。We only wanted a lower bound， so a lower bound is correct by inclusion exclusion principle。

It' probability of n。G than equal to one is at least this much。This thing that we want counted。

And so now we can simplify it。So， first is。SPro is sh shown in claim in the claim， right。

We get that this is two is 2 minus k。And the next one is。Size of F choose 2。Many X frames。And。

Both x and x5 going in the same bucket， that probability is 2 is 2 minus2 k。Okay。

 so we have done half the part。Probability of n greater equal to  one。 We have a lower bound。

 Next is to estimate。N greater than equal to 2。So， similarly。

Probability of n greater than equal to 2。Here we will need an upper bound because remember we will subtract these two。

 right。And we need a lower bound on n equal to 1， so it suffices to have an upper bound on n greater than equal to 2。

So， here。Just go over all the pairs xx prime。Right， because you want at least two。

To go in this bucket。So， this is。Simply smaller then。This event。X less than x prime minus is。

Which we have calculated， as before。So。This is just equal to S choose 2。2 is 2 minus2 k。 And so what。

 what you get is。Probability。N equal to 1。For random hash functions。

Given by changing big B and small B。 So that probability is probability。

N greater than equal to1 minus probability。And greater than equal to 2。Which。😔，Is at least。

It lower bound。嗯。S 2 is 2 minus k。Minus。S choose 2。2 is 2 minus2 k， and then you subtract again。

The same thing。 So two times this。Right， and you can check that。 this is。This is at least。

 this is at least a。By two is2 k minus S by two is2 k。Whole square。Okay， the first is S by2 two is2。

 the second is the square of that being subtracted。

You can check that this inequality is satisfied it's almost the same。

And what can we say about this now， So here we will use。The hypothesis。What was the hypothesis。

 The hypothesis said that s is between two 2 k minus-2 and two 2 k minus-1。Right。

 so that tells you something about s by2 is2 k its between one， fourth and half。So use that。

 It's more than half one fourth。And so， using estimate。You can actually show that。 This is。1 fourth。

 minus-14 square。Okay， which is grid then。1 by 8。So here you use the following property。

 basically show that。Show that this x minus x squared function。Is increasing。When x is。Les than half。

This so below X， it is an increasing function。So， using that。We get the lower bound。

 We fix that one fourth and get the value。 That's the lower bound because S by two is to between one fourth and one half。

Yeah， so that finishes this part of the proof。And so where we we have done the claim completely properties claim the hashing claim is done property is one。

2，3 now let us go back to the lema valian fazirrani。Let's continue with。

So Lamma proof continues here。So what is the lemma C demanding。That。If P has satisfying assignments。

 then we essentially show that。The satisfying assignments。

Will be reduced to exactly one satisfying assignment。And hence odd。So， let Phi have。N variables。So。

 randomly pick。K。Between 22 n plus one。Y 2 to n plus1， well。

 because we need property3 in property 3 we need S to be at least2 is2 k minus2， and we know that。

In the case of phi s is at least one， so we start we can start with k equal to 2。And go up to。

N plus  one。Because we don't know how many satisfying assignments there are， right so。Just guess it。

Or pick it randomly。So， randomly pick key。And B。And small B。Okay。

 so whatever we don't know we are just randomly picking， which is what is k， what is big B。

 what is small B that fixes the hash function。And once we have this random hash function， we can。嗯。

Look at。The bucket 0。So。What you do is output。The boolean formula。Soi。Which has。

 which continues to have n variables。As phi。And this extra condition that。X maps 20 bucket。So， this。

In case you are wondering this。Condition can be written as a。Bulin formula。So， write as a。

Write it as a boolean formula。It's not that difficult because you can think of。

A linear combination of x1 to x n using01 coefficients。Setting it equal to 0。

RightSo we say x1 plus x2 equal to 0。So that you can actually write as using and or not。Because。Yeah。

 the constants are just01 and the addition is mo2。So more2 you can write in terms of and or not。

 so do that。And then you have the formulas。Which is。

The boolean formula out which this algorithm a outputs Okay， this is a description of a。

That's how a functions。 So immediately， it is clear that。If fire is unsatisfiable。Then。

This and condition cannot。Give you a satisfying assignment， right it remains unsatisfiable。

So size is also unatitifiable。So S equal to 0 is going to s equal to 0。So， that is good。And。

Second property is。If phi is satisifiable。Then， let。SB the satisfying assignments。And。

It size is at least one。Well it is not an empty set。 there is at least one element。And， in fact， can。

We can write。The whole range。So the whole range is that2 is 20 less than equal to。Tourist to end。

 this is the range for size of S， right？And this is a set on which。The hash function does magic。And。

Makes the zero bucket。Singleton。 So let's check the probability。So， with probability。

With probability at least one by n， we would have chosen k。We would have。Qiuzin。😔，The unique key。

Such that S is between。2 is 2 k -2 and2 is 2 k -1。There is only 1 k and that k randomly if you keep trying then you will。

Fine with probability  one by n because K takes only。嗯。Around n n -1 values。

 So you will hit the correct one。 So condition on this fact。Or this choice。Condition on this event。

With probability。Greatter than one by8。We choose big B and small B。Such that。Number of xs。

Mapping to the going to the bucket view。Is one。Read this we have shown in Viian was。 this is exactly。

呃。In this claim number three， this is exactly what we showed， right？

That with probability 1 by 8 this。Will be one。 So which means that。You multiply the probability。

 so at least with probability 1 by 810。We would have。Ki。😔，B and B。 So hash function。

 we have chosen a hash function with this much probability。Such that。

Number of satisfying assignments ofsi is1。Okay。Henceor。Right， so。If I。If hash phi is0。

 then hash phi is 0， which is even。Otherwise， hash size is  one， which is odd。

And that proves both the parts of William Vaazzirani。So， this implies vt。Was it anylema。It。

 so that is a。That' is a great result。 In fact， it is showing not reduction to parity set。

 but unique set。So， we actually gave a。Randomized reduction。Of。St。So， it's a poly time。

Randomized reduction。Of Sa to unique set。Right， this is what we just showed。

That you can actually assume number of satisfying assignments to be either is one or0。

 only two options。If you can solve this problem algorithmically。

 then you can solve SAAT also in practice。And we also showed。NP2。Pit T P。Right， this。

These are the multiple interpretations of willin was in alemma。 But what was。Our original goal， so。

Our original goal was this。Theor of dota， right？Ponommal hierarchy。 So we， in particular。

 sigma2 N to the N。 What about that can we reduce N to the N。To Paris de set。

Which then reduces to shop set。So that we don't have any idea from this proof， right。

 so we we have to work hard on that。So。So， now， well。Use。This idea。Repeatedly。To random reduce。P。

 H2 par B。So， we intend to replace。They exist for all quantifiers。By a new quantifier。Parity。

So instead of using two quantifiers because they start alternating。

And then we don't understand reduction to shopet。Instead of that， we will convert。

Them to single quantifier， which is this upcoming new quantifier。Parity quantifier。

So it has this interpretation， this natural interpretation that。The variable。

 if it is acting on x so parity x， what is what does parity x quantifier mean it is true when。

The number of satisfying X's is odd。Okay， so we have in a way shown that their exist can be replaced by parity。

And we will also show that for all can be。Replaceed by parity。So， let us define it。

Because this will be now。Or。😔，Main notation。So， far。Bulan formula。😔，5hi x。Parity x comma Phi x。

This expression。So we are not seeing for all x 5hi x or their exist x5hi x。

 we are seeing parity x phi x。This is true。If。The number of。X is that5hi phi。Iot。Okay。

 that's the definition。Number of these xs on which parity is acting if this is odd。

Then this quantification is true。And。No。Even alternating they exist for all。

 we convert all of them to。The single。The single one。So， let's。

Trite that down the results we intend to prove。So let's just call this lemma parity。Let's see。

 be a constant。There exists。Polyt tuing machine， M。Or polyum to machine a。Such that。For every。

Quantified formula。For every quantified。For every formula。😔，fi。我使。😔，With C alters。

Please see alternations of their exist。For all。We have。The following two properties。

So first is if size is true。😔，Then。Probability。Of this randomized reduction， right。

 So it uses random bits R。And the input instant psi。This is parity set。With a decent probability。

 with a very good probability， in fact， two third probability。And in the other case， whens falls。

Then the probability of this is。Much smaller， less than one third。So note that this is。

This may may make a mistake， both sides。Right in true， also， there are some mistakes， false。 Also。

 there are mistakes。So both sided errors are possible。So the error is happening。

More error is happening than brilliant Poanni， because of。When you convert for all。Okay。

 then both sides， there are errors。 So we'll finish this proof next time。



![](img/5ad536adfd421f3888b2e23e5438be27_2.png)