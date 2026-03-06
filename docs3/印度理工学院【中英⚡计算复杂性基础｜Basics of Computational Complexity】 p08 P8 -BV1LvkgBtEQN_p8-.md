# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p08 P8 -BV1LvkgBtEQN_p8-

![](img/a5e0aec28d22d2f3540359c334dde656_0.png)

Okay， so。That is the definition of NP。This was。Essentially given by cook and Le independently。

Inspired by these optimization problems， which are。It seemed hard。But yet， when a solution is given。

It's easy to verify。So。Yeah， so such problems。Are called an NP or N collects all those problems for which there is a poly time during machine M。

Which given this certificate you。Can check whether use the correct answer or not。Okay。

 so let me mention here that。This M is called the verifier。Touch the verifier。And this you is the。

Certificate for x。So verifyifier and certificate。And。This blow up is polynomial。

so if you look at the length of u， it's not much bigger than the length of inputex。

These are the import key points of the definition。 So let's do an example。So in the， in problem 2。

 which was sub sum。Subsid is a certificate。Right， you are given T。And what is the certificate of T。

 it is a certificate subset。Who sum is。D。So this L that we talked about in the definition。

 this corresponding L is。Scom tea。Yeah， so that S。Has sub。off心啲。So want input S comm T。

What will the verifier do。The verifier basically guesses this。Certificate。Certificate， you。Is。

The subset of S of some T。And verifier M is。Is the tuuring machine。That given S to U。

So given S and T and the subset U。Checks whether。Checks， whether。

U is a subset of S and sigma U is equal to B。Thats all okay， so verify M is trivial it just。

Just checks whether use a subset and whether this elements of U sum up to T。And hence。

 by the definition， it means that。L is in N。You can check this thing。 The other conditions also。

 you can check that。The size of you is smaller than。The size of S comea tea。

Right obviously because S was in the input and use a subset so it sizes are pro bounded。

There is no size blow up in the certificate。And M is polytime。So overall。

 what you get is by the definition you get that L this L is in NP。And similarly， with one in three。

Okay， so all these problems。Decision problems。 they are in。

NP by the definition because we have shown both certificate existence。And verifyifier。

Now note that if the certificate doesn't exist， it is a no string。Right。

 so this definition doesnt talk about no strings。Well or I mean it talks about in this way its an if only if condition。

 so if x is not in L， then there should not be a certificate。Okay， but that is clear so。

Thats the part which you will generally not care about。But when x。Is inel。呃。

The important thing is that there is a certificate。Easy to verify。Yeah， so now let's place N P。So。

 various N P。So the first claim is that。😔，Pace contained in N。

And second will be that NP is contained in X。That's the placement。OkayN P sandwich between P and X。

The easyas part is that P contained in NP any problem that is efficiently solvevable also。

Has a certificate and verifier。Read the。The solver of the problem is itself also a verifier。

 So that's the trivial part。 slightly more non trivial is。W is N p next。Theyre the。

 they also the idea is simple。 You just have， you just search for the certificate。

And the whole space。Okay， and just count the measure the size of the search space。

 Itll be exponential。So。Let's prove the first part。 So say L is in P。So， it is decided by。

Poly time tuuring machine。M。So then， for all eggs。For all inputex。X is in L， if and only。N X is one。

So a string is a yes string if you only leave this particular solver。

This efficient algorithm M accepts it。 right This is by the definition。Of m。

So whats the certificate here you can take the certificate U in which was in the definition of MP that certificate you can take as the empty string。

Okay， the verifier M。Think of M as a verifier with empty certificate。So， with u equal to。With M T U。

M can be seen as a verifier。Which means that。Eison N P。OkaySo this is the trivial part， P in。

Bs an in。Every L which is in P is also in NP， this means that p is a subset of NP。

It's a sub complexity class， if you will， of NP。That is the easy part now。

 but N may also have heart problems， right problems which are much harder than polynomial time。

Like this subset some。DB。Integer programming， so what is an upper bound on them？

Upper wound are these brute force algorithms， which are in X。So let's now do that part。So now see。😔。

Eliin。And B。Vid。😔，X in L。If and only if there is a certificate to you。And this verifier M。

 some verifier M。Excepts you。Right maybe to avoid confusion with the old L and M， let's。

 let's call it L prime and M prime。So take a problem in NP and then for yes， strings， x。

There has to be a certificate。Vfiable by a fast steering machine and， which is the verifier。

In timeim。The time of tu machine and prime has to be polynomial in n， right。In N to the D。Constantly。

Okay， so this is what is。Given to you， this is the。Hypothesis that comes from Lp being in Np。Now。

 y is L prime in x that is what we want to show。嗯。So， we will look at the brute force algorithm。

 what will the bru force algorithm do it will try to go over all the use。Right， so go over。So。

 searching you。Takes。Two race2。And there is two sea time。It you。Is a string or of length and to see。

So。You can search for it。This is basically coming from here。You is in 0，1。X to the C。

As U is in 01 next to the C。 So if you look at the whole space， search in the whole space。

 then it's to to end to C time。And for each。Choice of you。 you will。

Run employment and check that will take。Endia to time。So， brute force algo is。

To race to and race to see many。Possibilities of the certificate。And。And waste to time for each。

Actually， what happens is this U is as large as n to the c right。

 so this will take time slightly more time it will take n plus n to the C。And this thing is to be。

 right， So it takes this much time。So first the， I mean， the certificate blows up slightly。

Then when you run em on that。呃。I cannot maybe do it in two steps。So the input of m prime is x。

And X to the sea length。And in terms of the input size of em， it time is。Raace to be。

So which you can write on the next page。Right， so that is the time complexity2 is to to C times n plus n raised to see whole thing raised to d。

But notice that this is still exponential in n。 it's not more than exponential。So。

 this is actually less than。Dorisu。😔，En raise 2 C plus 1。Right。

 you can check this because C and D are absolute constants and N you can take larger。So。

 you check this thing。Is this truehu。And once you have checked this。This finishes the proof。

 It's an exponential time algorithm。It means that L prime is in。De time。2 raised，2 and raised。

2 C plus one。Which is clearly X。Contained the next。Okay， so did that finishes the。Second part。

 of course， this means what。This means that。And please contain dx。Okay。

 because we have done this for every language in MP。So。

 every problem in P is an N and every problem in N is solvelable in X。Okay。

 but X P is not good enough。 This is these are very slow algorithms。

 These are really good force algorithms。So， that's the open question。It's unknown。Weer。And B。

Is different from。The other two。Okay， so。You can ask whether， you can ask whether P is。

Strictly smaller than N P。And you can ask whether N is strictly smaller than X。That's the conjecture。

 which usually we make that。NP is strictly between P and X。Okay。

 not all problems of x can be solved in N。And。Not all problems of NP can be solved in。Pllula咩 time。

But one interesting thing is that these two endpoint， P and x， these will will separate。

In this course。Okay so。Later， we'll actually be able to show。That P poly time。

 exponential time are actually different classes。So which means that there is。

A big margin between P and X and。And。But you don't know whether NP is closer to x closer to p。

those are。The open questions。So what does an。N P stand for this。 We did not。

I did not tell you what does N stand for， So N stands for。No determinism。So， the N。In N P stands 4。

Non determinism。Okay so non deterministic polymial time that is what that is what it means。So。

 why is it why is such a thing called non deterministic polynomial time that is a better name would have been efficient efficiently verifiable。

Instead of that， why this complicated name。So this to answer this question。

 we have to define a whole new。model。Which is called non deterministic Turing machines。

And I think that also you have seen in probably seen in other courses。So。So。

 we will shorten this to NDTM non deterministic tuuring machines through contrast with tuuring machines。

 the term which are which we think of as deterministic。嗯。

So the definition of this will be similar to tuuring machine， except。

Transition function will not be a function。It will be a relation。So， N D TM。Is similar to。

ding machine。Except that。Nao。There are two transition functions。So， we have。Alphabet。States。

And two transition functions， delta is 0。Delta 1。Or you can also think of this as there being。

Transition relation。So what is the difference between transition function and transition relation？

Well， in the function， once the configuration is set。

 there is only one way to move to the next configuration。

In the transition relation with once the configuration is set。

 there might be multiple ways to move to。The next configuration。

 they might be in multiple next configurations。That's why it's a relation。And in fact。

 it suffices to， as you will see later， it suffices to just assume there are two options。

So first option is given by or let me say zero with option is given by Dlta 0。

And one eighth option is given by Delta 1。Okay， so function becomes a relation essentially。And。

So at any configuration C。Its transition is no more unique。So it has two loud moves。To， in fact。

 this。Eny team。Has two allowed moves。1 following delta 0。And the other。Delta 1。

These are the two moves。What if now given a configuration at which one of these will the clearing machine choose。

So that we we don't say anything about the choice。Okay， the tuing machine can take any path。

 There are two paths。And well only make a statement about what happens in the end of the computation。

Okay， so this， this is a more fuzzy。A computational model。 That's why it's called non deterministic。

The the steps are not determined。嗯。Like we defined interior machine。Su。😔，N DTMM。Excepts。

In protecttex。If there exists a sequence of choices。Leading to the。Except it。And output  one。

That we can set as a convention。Okay， so that's the。Condition we are putting that there should be a。

Sequence of choices。So the first choice say that NTM M makes delta 0 then delta 1。Then delta 0。

 then delta 1 and so on。And reaches the accept state halls and outputs 1。Then we see that okay。

 since there is some path。2 acceptance M has accepted x。Okay。

 so M is not supposed to accept on all the parts， just one path。

And what is the negation of this the negation is all past reject。Denim rejects。

So if there does not exist。Such a choice。Dm。I said。To reject。X。And output 0。Okay， so that's the。

N DTM setting。Okay， there are choices at every step。And if a sequence of choices leads to accept。

 then output is1。Then we say that， actually。It's a yesing。If there is no accepting path。Then。

 it's a no string。And now since we don't talk about how the choices will be made。

This is not really a practical computational model。Okay， this is really。

 this is as theoretical as it gets。It's not a practical one during machine is like computers。

 but this。Is not like computers。So what's the definition of time。So， time taken by。M on x。Is。😔。

The maximum。Number of steps。By M。To halt on next。Okay， so this is a bit。Sensitive to the。

To the steps， I mean you。We are looking for we are going over all the accepting parts and what is the longest。

Okay， that defines the。嗯。The第。Complexity。Of entity him。So， this maximum is over。Oh。

 this is not just accepting parts， sorry these are all parts。

So what how much time will it take to haul Because remember if x is a no string。

 then you have to go over。All the parts and see that all of them are rejecting。So this。

 so actually this is maximum。 This is where it is maximum over all the parts。So， max over。

All possible。Bts。Okay， and based on this， we will。嗯。Well redefine and P next time。



![](img/a5e0aec28d22d2f3540359c334dde656_2.png)