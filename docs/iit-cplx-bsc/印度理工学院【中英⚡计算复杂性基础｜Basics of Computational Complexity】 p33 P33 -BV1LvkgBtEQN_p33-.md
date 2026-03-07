# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p33 P33 -BV1LvkgBtEQN_p33-

![](img/15f2a1e28c263b483e3401f30a30f6e1_0.png)

So recall that we are in the middle of Toda theorem， which says that。

Polynommal hierarchy can be computed。Using shop set。So for that， we defined this partP class。

And we showed that。St can be reduced to unique set， and hence。Paity set。

This is the vian Varani lemma。Which actually you used hash functions。 Okay。

 so the satisfying assignments there hashed。Two buckets。And the bucket，0。Will。

 with high probability have。A unique， satisfying assignment。 That's the idea。And。It yeah。

 So NP has reduced to PerTP。And now， we will。Convert N to the N。

So this reduction is you can think of it as NP reducing to shop set。呃。Which is not very interesting。

 but unique set is interesting。And the interesting thing will be that this parity will now。

Be used as a quantifier itself。O， well replace their exist for all。With this single parity。

Quantification。So lemma 1 will be about parity。quantantifier。So， letsi be。

A Boolean formula on top of which you have see they exist for all。Alternating quantifiers。

So we will convertsi into a formula A R commsi。Which will be in parity set with high probability if psi was true otherwise。

With low probability。 Okay， this is， this will be both sided errors。 So let's do the proof sketch。So。

 the idea is。Replacease the。For all， they exist。Quantifiers。1 by one。By the。Parity quantifier。

And do induction。So， let's induct on。Buling Form say。Which has， let's say， parity on top。0。

1 to the L。So strings that in 01 to the L space。And let me remove this part。So first。

 there is a parity quantifier， then there is a there exist quantifier。

Then there is a for all quantifier。And the formula is Phi zx W。Right。

 so three strings differently quantified。Well convert this There exists to parity and then。

For all also do parity， in fact， all three into single parity quantification。Now。

 let me write down the domain。 So this domain is01 to the L。This is 0，1 to the n。And this is 0。

1 to the k。So now buy the valiant firrani technique。We can get a formula。Dao。

Such that for random string R。The probability。Overar。So now parity。

 so basically what will convert is willin franni will convert the they exist quantifier into parity。

 right？So they， they exist X will become。Pity x。And then， there will be。For all the blue。Fai。😔，And。

To Xer。Is true。With high probability。So， this is the part。

This tau Xcomoma R is the part which it comes from the hash function when you express it as a boolean formula in vian Wzirani proof。

Right， and so this happens if。They exist x。For all the blue。F is true。

If that part of the formula is true。Then actually they exist can be replaced by a unique x and we have and hence we can replace it by parity x essentially there is a single x which will satisfy this。

嗯。Moreover。This probability will be 0， if it is false。And。Or file。Probability over R。Pity x。

For all the blue fire。And tau X R。So， this is true。This probability is 0。If。That formula was false。

Right，That is the full v was in any result。That true with high probability and false。With certainty。

When the formula is true respectively， when the formula is false。So， which means。

That now on top of this event or this expression， what happens when you add the parity Z quantifier。

 So when you add the par Z quantifier for a single z， the probability is1 by 810。

So if there are tourist to well sets， the probability will be worse。Okay， so that is。

That is what you get。Sup probability over our。For parity Z and this。Expression。Yeah。

All you can say is this is greater than equal to。1 by 810 to the。Tourist will。If。😔，The formula，si。

Which was paraized their exist X for all the Phi。Sorry， this is that。P said， they exist X。

For all the bluesi is equal to true。So if size is true。Then。This modified formula with parity。On x。

Although there is some positive probability， where it' is very small。It's not as big as1 by 8。

Because。Z is coming from 0，1 to the L space。So for every Z， you have to。Ensure that this。

Transformation is correct， and that happens with multiplative。Probability。

 so although we have reduced。So， this。Randomly reduces。Sai do。😔，Paityedex。For all the blue5。And Zou。

But the success probability is very low。Okay， so this is not satisfactory because we cannot call this。

Efficient reduction。Randomized reduction， unless the probability is good， actually， in the lemma。

 we want the probability to be two third。So in this step。

 the success probability should be very high。Something like a constant。Do third。

So how do we increase this probability， That's our current question。

So how do we increase this probability from。1 by 8 to the 2 to the l22 thirds right That is the question。

So。The thing we have to do is somehow for every z。We will significantly increase the success probability。

From 1 by 810 to almost close to 1， so that will be the idea。So， for a fixed。Z。Bring the probability。

Let's bring the probability close to。Vn。😔，Let's implement this。Su。For a fixed set。

Instead of just one random string or one experiment are you do T experiments。 You cant take an hour。

 if any one of those experiments is true。Then， we are good。Okay， so do these M。

 many experiments and take take an R for a fig set， repeat the transformation。T times。

For random strings。R 1，2。RRT。So what happens So you we are looking at probability over。R12 R0。Or。

For all these。And。So now willin wasrani for many。R is。 So basically， this stary is。Do Xcomoma。Okay。

 so run this for various random strings or 1 to r0。And then， take an or。Overall， these。Jicks。Okay。

 and whether this or is true。That's what you are checking， whether this or is equal to true。

 So what is the， what is this probability now， So this is。See this event。嗯。Is one minus the event。

That all of them are false。RightBut what is the probability of being false that is 1 minus1 by 18。

And that T times。K that error has to be repeated t times。 so the probability of error is。

1 minus1 by 8 to the t。Subtract it from one。Okay， so if you take tea very large。

Then this probability is very close to one。Because a fraction needs to be。Kind of becomes 0。

So this probability becomes kind of one， of course， assuming that the original formula was true。If。

the exist X for all the blue Phi is true。Ils。The probability of the same thing。

Probability of this expression being true。When the formula was false。That is 0。 That is not0。

 That is that is the error case， right， So that's1 minus1 by。A1 is the error。T times。

G for the false case， something being true。See， the original formula was false。

 but one of these experiments comes out to be。One of these comes out to be true this probability here。

😔，In case the。For bos。False。Right then all these instances of vant vanni that you do for R120。

They will remain false， no matter how many times you repeat them。 So the or will also be false。

So chance of that becoming 0 is actually。Of it becoming4 true is actually 0。Okay。

 so that's the first。 That's the key observation。They are in multiple experiments。

Going from true formula to all of them， all two of them false。That probability is very low。

And going from falses。Coming from falls， going to this tea。嗯。Being false， that probability is one。

That's where that's what we achieve。So， this is called。Probability amplification。Kd of success。

Probability has been amplified。 The error probability has been。Brought close， closer to 0。Now。

 let us。Consider the zs。So this we did for a fixed z Now let's keep changing Z go in the space01 to the l。

 So then the probability。Again， our want to。or地。Pity said。Or even to tea。One of these is true。

M this whole thing。Equal to true。So what is this probability。See， assuming。

That the that to begin withsi was true。Lets assume that the size is true。 So in that case。

 this par is a。Or operator par X。Willin Vairrani sub what is the chance that all of them is all of each of these is false。

Let us just compute that probability。So these are tea experiments mistake。

The error probability of one experiment is 1 minus1 by 810。

And so 1 minus1 by E10 is the error probability for one。Experiment do a t time。

 So it eras times t moreover。Look at these zs。Right， which were。Making sight true。So if these。

 the number of these zs is tourist well。Okay， so that also we have to multi take into account by union bound。

So， that is the union bond。Acting。So again， going over all these good sets。

And for each these two experiments。The error probability is upper bounded by 1 minus 1 by 80 to the t times2 to L。

So the success probability is inverse of that1 minus that。Okay。

 so this is what we want to make sure is high。And。What happens otherwise。So， if。Size false。Then。

 what happens is。When you consider this probability。We want。 So this is the error probability。

In the false case， this experiment giving you true。That's an error。 So when will that happen。

See if you again go over these zs。Which were。Since the formula was false，si was false， it means that。

The zs number of zs where you get true。Is even。So， you go over those。And in those cases。

 one of these three experiments given you。Giving you true。If you calculate that probability。

 you will get。Upper bound tourist2 times1 minus1 by 810。To the底。Okay。

 so the error probability will be。Will be this much。

So basically consider the zs when the inner formula is true and when it is false。

 so what happens with the false case， the false case will remain false。What happens in the true case。

The true case， giving you。嗯。Giving you true。Read that。That the tro is giving you false。

 That probability is。Is1 minus1 by 810。And from that， you can calculate。This upper bound。

So let us now analyze this for P。So now you take tea to be。Quite large，16 N L。So， that will give you。

That two is to l times 1 minus1 by 810。To the t as t increases again。

 this expression should tend to 0， right That is the rough intuition。So， you will get。

You have to estimate this。E10 times 2。That's 16。Anil。So。

 1 minus1 by 8 n to the n for large enough n is at like1 by e。So you get two race to， in fact。

 it's less than equal to。いいです。Wenbaiyi。Weto well。E is around 2。78， so this is definitely less than。

One third。Okay， so this error part is less than one third， so。In the true case。

 you get two third success。And the same thing when， when size falls， you get error to be one third。

 success to be two third。So which means that。We have randomly reduced。Cy to side prime。

So what is Cyprime Cyprime is。Pity z。I want to tea。3 experiments， T instances of vin Vairrani。

Inside ispars。For all the blue Phi。And。Dao Xcoma。Tau Xcomoma。Right， and。So， this thing we can call。

This we can call fire Eedx。It just depends on Z x and。

And our rise So we are calling it Phi is that co my X。The only thing， which is extra。

Is the or operator。Right， we have almost reduced it to single parity。Quantification。

But you also have to now remove this。Or。So， we now remove。The or operator。So how do we do that。

 So let's consider a simplified。Or which is or of two expressions with para X。A simplified situation。

So parity x。If phoix。Or pary X， a parity y。F 2， y。So now here we will show the idea of removing this or。

Okay， it is all of parity operator， So we how do we convert this into a single parity operator。

Or single parity quantification。嗯。So this will be a bit tricky。嗯。Weers。Introduce some new variables。

 and the。Try to。Ang。😔，Modifier is F1 F2。And， actually。Then take and of the modification。Su。

So always remember that this first part is saying that either。If one has。

Od number of assignments or satisfying assignments or f2 has odd number of satisfying assignments one of these。

 right？So it's also possible that first has odd the secondness even， so it might make sense to。

Let's do the following。So， introduce。New variables。U1 U2， U 3。And。😔，A plus one operation。On formulas。

So what will this。Plus phone operation B。This is as follows。For formula。Effs。Define F plus 1。As。

So it will be two cases u equal to 0 will be just F。Or you may set you to be one。And fix x to be 0。

Okay， that is。The plus one operation， what it is doing is。It's。

Just growing the number of satisfying assignments by one。 So let's write this down。It grows。

The number of satisfying assignments。By one， that is。

If you look at the number of satisfying assignments of F plus 1。Then you get the original thing。

 plus one。In a number of satisfy assignment has grown exactly by one。Now， how does this thing help。

So if you start it with F1 even， it becomes odd。And if1 F2 was also even， it becomes odd。

So you can multiply the two so you get odd。And again。Addd a plus one， so that is even。Okay。

 so even even can be mapped to even this way。Any other combinations like even or or even。Or ordered。

They will all go to。O。So， let's write that down。So going back to。嗯。What we heard before。Paity X， F1。

Or。😔，Pityity Y F2。Definine。Pity of X， y。U1， U 2。You 3。And use plus one， three times。

So you have F1 plus one。Formula。F 2 plus one formula。Take a conjunction of those two。And then。

 do a plus  one。Okay， so this is in。X U1。This is an X U 2。And this whole thing is then in x。Sorry。

 it's not x U2。 This is y U2。And this will add。You 3。So you will have x， Y U1 u to u 3。

 three variables have been added new variables。And you can see that。In case iPhone F2 both have even。

Number of。Or see so when is this formula。False。It is it is false when the number of solutions satisfying assignment should be even。

So even would mean that this product F 1 plus1 and f 2 plus one is yes， how many times is it。

That counting you have to do。So， let me write down。So， this is true。If and only par T x。ifwen。😔。

Or the other one， parity Y F2。😔，Is true。Only when F1 and F2。

 F1 or F 2 have odd number of satisfying assignments， then。Only in that case， you will get。Od here。

If both of them are even。Then this product will be odd and odd plus one will be even。ok。So this。

 you can， this， you can easily prove。So。It just follows from this odd times odd。Plus， one is even。

While anything else you do， even times odd。Even times， anything。Anything you put here。Will be odd。

Just use this。Property okay， odd times odd plus one is even any other combination plus one。Is odd。

 so that gives us a powerful tool and now well use it。



![](img/15f2a1e28c263b483e3401f30a30f6e1_2.png)