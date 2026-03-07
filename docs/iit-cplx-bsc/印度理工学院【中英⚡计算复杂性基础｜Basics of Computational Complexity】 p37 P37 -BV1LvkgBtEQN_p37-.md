# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p37 P37 -BV1LvkgBtEQN_p37-

![](img/f5c3e4979df76c9be73effc56d816498_0.png)

So。We have shown that ZPP is in Rp and Co RRP。what we did is we constructed this empire by truncating the。

Computation， after a while。Right three times， though。Expected runtime。Now， we want to show the。

The other side， which is RP intersection core RRP is in ZPP， so we will have two algorithms。

And we'll run them together。Let's do that。Solect LB now in R P intersection， Co RRP。It'd be decable。

Let L be decideable by。Probabilistic tuuring machines， M1。Respectively M2。

It time polym into the C for constant C。So let's define a new PTM M。So what will。M2。

 it will simulate both M1 M2。S speak。Random or。R。😔，Inwen。On x with this with random stringer。

As the random。Choices。And。😔，M2 x， R。Okay， you can do this sequentially first run M1 x commar。

 store the answer， then run M2 xcomar store the answer。And if the answers are the same。

Remember that these two are Rp Co RRP machines。 so they will stop after some。After this time。

 right enter the C V resumes， after enter the C step， theyll stop。

Then you check whether the answers are the same。If they are。You should output。The common decision。

So if both of them said yes。Say yes， output yes， if both of them say no output， no。

 So intuition for this is on a yes string。呃。RRP machine， the Co RRP machine。

 which is M2 on a year string M2 will give the correct answer。And on a nose string。

M1 will give the correct answer， right， because there is one sided error。

So that is why if both answers are the same， then you have the correct answer。Els。

You don't know what happened， so you have to abort and repeat the experiment。

So you have to go to step  one and then repeat this experiment。 Okay， so let's analyze。

Suppose x is a yes string。So M2 has to say yes。Or maybe I say one。

I'm identifying one with yes always right and 0 with no。 So M2 has to say one。Because。

M2 is coming from。The Co R P。Property。So it cannot make a mistake on yes instances。

 It has to say yes。And what that means is probability。Over the random string。M1。😔。

What can you say about M1 So M1。Will not be yes will not be1。With small probability。

The other probability of M1 making a mistake is small， okay。So。Yeah， so on the yes instance。

 M1 may make make an error， this is by definition。You take this as a definition。

Of M1 M2 so M1 makes an error on yes instance with low probability。

And no no error on the no instance。That we will use。In the second case。

An M2 in the yes instance doesn't make error， so。M2 will say yes， and。M1， missing say no。Loer。😔。

If M also said yes， then you will。Exit any output， the correct answer。If it says0。

 then the this algorithm m。Has to be repeated right step  one will be repeated。

So let's analyze that case。So what happens in tea steps。So in T rounds of step 1。You。😔。

Get the probability。Over these choices， R 1， R T。A one always saying。哦。Ziru。Okay。

 which means M1 making a mistake again and again t times。That is smaller than three race to tea。

1 by three is2。Right because every time you are using independent random strings。

 so better probability is one third multiplied that many times。 so which means that。

The expected number of。Rounds。So there will be t plus1 rounds。

Meaning that the first T were all wrong。 So thats of that is probability1 by。3 is to be。

And t can go from 0 to。Anything。Right there is no upper bound on how many rounds there will be in this algorithm M。

But notice that this t over 3 rest to T is actually even with infinitely many steps。

 it is this is a bounded quantity。This is， actually。Constant。Okay。Just do this as an exercise。

So sigma 1 over 3 is2 T is bounded。By2。And even t by 3 is2 t sum is bounded。

Because this denominator is going much faster than the numerator basically。

So number of rounds is expected to be constant。Okay， so think of 10 rounds。

 So in 10 rounds you expect。A correct output in step 3。And which means that the time complexity is。

Pretty good。That's what you reduce。this implies that the expected。Time complexity of M on x。Okay。

 this is polynomline into the sea。So it simulates M M2 and simulates it。Infinitely very times。

Infinitely infinite many steps， but in actually the expectation is only polynomial。And。

The keys of x not equal to L。Is similar。Okay， so in both the cases， yes or no strings。M has a good。

Expected time complexity， which means that。We have shown El Z P， P。

Which means that any problem in the intersection。Is in0 error。Okay， so that is what property to。

Demanded。And from property2， you immediately get that Z P P and R P intersection Q RRP are equal。

 Okay， that follows easily。Okay， so。So that is a very good comparison。And the open questions are。

 yeah， whether P and ZPP are the same。And the other side。 So let's state the open questions。

So it is expect in the。Conjecture we make is that actually p is equal to Z P P。And similarly。

 the conjecture we make is set P P is not。And P intersection， Co and B。Okay。

 but these are open questions。 So Z P Ps should be closer to P than from。

And P intersection co in people its not known。 None of these two things is are。Non。

 so next thing we will discuss is， is。Ited less than one third。Les than equal to one third in B， P P。

Important。Can we talk about error。呃。Any constant below half。Okay。

 or let us say polymly close to inverse polymly close to half。So what about。

Eror less than equal to half。Plus， let us say enter to the sea。Okay， in terms of input size。x。

And some constant C So this is inverse polynomial。 So if you are very close to half by very。

 I mean inverse polynomial。Then。Is this error too big or will you still get BP？

 you can ask about these questions this is related to what is called probability。

Boosting of probability amplification。We now show。How to boost。The success probability。

How do you boost it， you boost it by repeating the same experiment。

 you repeat the experiment again and again and then take a majority vote。

So this is the topic of probability amplification。If you had if you have done a probability course before。

 you would remember turn off bound。Okay， so we essentially will use certain of round and show that majority vote is good。

So what we will show is what we will see in the end is that the two third。In the definition of。B。

 P P。嗯。So this was in the definition of。Also in RP P， we had two third。And in B P P。

 we had two third。Yeah。So。Two third in the definition of probability classes， probabilistic classes。

Is arbitrary。Okay。So， in fact。We can use any。Fraction。That is。Inverse polynomly。

Inverse polymial away。From half。OkaySo you need an advantage more than half， which is。

Just in words polymial。Advantage。You don't even need advantage like two third or strictly because then half by a constant。

 So that's a very useful theorem to have。So， this is the。Amplification theorem。

So lets probabilistic during machine M。Decide ill。Such that。For all X， X is an L， if I only leaf。

Probability that Mx R is1。Over the random bits are random string R。Is just marginally more than half。

Ss half plus one over。X to the C。Then。For all D， there exists。

A probabilistic tuing machine and prime。Such that for every input。X is in L， if I will leave。

Probability。That M prime。Except sex， the success probability is significantly more than half。

 its close to one。Okay， so this is close to one。So the point is if you start with success probability close to half just above half。

Then you can boost it up almost to one。Okay， so starting from success probability just above half you can reach。

Just below one。Okay， obviously， this is just above and just below you have to quantify。

 we have quantified it properly。 So above half， you need inverse polynomial。Advantage。

And then you will reach one by。An exponential amount inverse exponential。

This is a very strong theorem。Okay， this is inverse exponential。

So it very it sit it is approaching one rapidly。As you look at bigger and bigger input。

So for practical purposes， this is really no error okay it is 100 percent correct answer。Almost。

So how do you prove such a thing。So details of this really fall in probability courses。

 so I will not go into those details。Algorithmic idea is simply that you take this probabilistic machine M。

And run it。T times with。Independent。Ours， independently chosen random strings。

And then so every answer will be yes or no， you take the majority vote。

 So if yes appears more than t by 2。Your output yes， otherwise， no。And this will have。

This answer will really be robust。 Okay， it will have a very high probability of success。

That's the key I algorithmic idea to remember。Suran M。😔，K times on x。With independent random bits。

Or random strings。And output the。The majority value。And in the probability analysis。

 use churn off bound。Use turn off bound。To analyze the error。The error probability。 Okay。

 so let's define the。This new algorithm or。BDm。So define this new PM M prime。As follows with the。So。

 we will pick k to be large but not too large that will come from churnov bound actually。

 so lets take k to be。8 times the size of x raised too deeps2 c。

What are c and D So C is this inverse polynomial advantage over half and D is this inverse exponential。

嗯。Distance from one。A closeness to one。Right， so based on that， you would define K and。And then j。

 as I said， just repeat。So a repeat and majorities on inputex。Run M X。K times。

With independent choices。Okay， so the IID is for independent identically distributed。Randdom bits。So。

 let the outputs be。B y 1 to y k。Okay， respectively for each。Execution of M X。

Just output the majority of this。Okay， so y 12， Y K R 0，1 or yes， no。Whichever appears more than。

G位 do。To break the tie， you can think of K to be odd。Okay， I can just define here。K to be this。

And so case odd and hence there will be either yes or no will be in the majority clear majority use that so。

M prime is very easily defined， right。Using M， it's just repeating the experiment M many times。

How do we analyze the。Atder probability now。 So let's do the analysis。So， for I。1，2 k。Define。Xile。

So define this random variable。Xhai。To be 0。If wire is wrong。And one otherwise。If5 I is。Right。

So X is just an indicator variable。Now， since Y comes from a random process。

 so we can call it a random variable。It's1 if y was correct，0 if y is was wrong。

And what we are interested in is。Can think of it as sum X。So what is sigma。Xi。😔，In fact。

 we are interested in。What is the chance。That sigma X， I。Is the。It is sum of zeros and ones。

 right and we want ones to be more than K by2。 So what is the chance that it that that doesn't happen。

It's less than k by 2。That's the bad event。Right that the number of ones is actually less than majority。

 so you want to estimate this。Probability， that is the error probability。Based on the。

Success probability of M or the error probability of M was just below half。

Right inverse polynomial away from half。So based on that， we will。Estimate this sigma X。Next time。

 using Chov Bo。

![](img/f5c3e4979df76c9be73effc56d816498_2.png)