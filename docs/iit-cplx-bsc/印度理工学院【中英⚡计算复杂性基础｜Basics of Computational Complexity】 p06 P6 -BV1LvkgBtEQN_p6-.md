# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p06 P6 -BV1LvkgBtEQN_p6-

![](img/a18899a7f2546726c92bedeb80f8f128_0.png)

This is the whole team problem。Set of those strings， which correspond to a。

To a tuing machine and input。And then this particular Turing machine should halt on that input。

With an output bit。Okay， so basically recursive problems with an instance is given to you。Now。

 can you design a tuuring machine。That's the question， right。So， it captures。The Guin。

Is there a tuuring machine。To test。Weather。Ml for H Sox。Right， so this is the question which we are。

Formalizing here by defining the language hall because the yes strings are。

The ones where ML for holds on x。So if you want to recognize this language， decide this language。

Then you have to design an algorithm to test whether MLhi is actually。Going to halt on X。

And the problem is that when you are given a bad input where ML alphapha doesn not halt on x。

 what will you do because it is an infinite loop。So it's， in other words。

 you want to test for infinite loops。And that is that looks hard。 and， in fact。

 will prove that it's in。Completely interacttractable。 There cannot be a solution。So， it's a。

Uncomputability。Was shown by church。Which was a very tedious proof。Nearly a century back。And then。

Much simplified。By tuuring。So， alllan tuuring。When he define this tuuring machine。

 which we now call Turing machine。Problem， the proof of halting problem。Being uncomputable becomes。

Became very simple， as you will see now。So， halt is。Not comp。Rof。😔。

So suppose it is decable by a tuuring machine M0。This is the proof。

Will go via con will go by contradiction。 Suppose it is computable。

 and then there is a curing machine M0， which is deciding halt。

 which means after finite many steps it。Can tell you whether M alpha holds on x or not。Say。

 it outputs。Wen。On alpha comma x。1 on alphacom x if。M， L phone exs。0。If M L5 x doesn't hold。

Does't hold means it goes in an infinite loop。Okay， so， so what can we do with this？With disinform。

So， actually。The impressive thing in the proof is once you know that this during once you have assumed in this case。

 that M0 exists。You can actually feed M0 to M0。Okay， that will。Give you the proof。

And that will actually first give you a contradiction and that will show that M0 cannot exist so that what happens when we feed M0 to M0。

So， let's do that formally。So define duringuring machine and prime。As follows。So， given input alpha。

If。M01 alpha comma Alpha is 1。Then， output'll put1。

Okay so what is what is the behavior of M prime so M prime takes input a string which you should think of as a description of a turing machine。

And you feed alpha。On the input alpha of alpha and alpha to M0 as input。So， basically。

 M0 will simulate。The Turing machine described by alpha on alpha itself。Right。

 so here we are actually sending。We are trying to see M。So let's go back to the definition of M0。

SoM0 is a tuuring machine is an algorithm that decides halt right？When will M0 alpha alpha be 1？

Only when。In fact， if an only leaf， M alpha holds on alpha。Sorry， it should be the opposite。😔。

That is the beauty of it。Doesn't hold。If M0 doesn if M alpha doesn't hold on alpha。Then， empire will。

Neggate the answer。 Okay， now put one。What if M L4。Hson alpha。So， in that case。Simulate。

M alpha on alpha。Computation。An output。The negation of what you get。Okay。

 so this completes a definition of M prime what em prime is doing is it is。Exploiting M0。

To check whether M alpha。Is going to。Halt on alpha or not， on itself or not。If it doesn't。

Then it outputs  one。If it does， then it neggates the answer。That is sampling。

 so what is the contradiction？Well， we still don't have a contradiction， but we have。

A curing machine we have defined M prime， which is doing something funny。

And contradiction will come when you run， as I has suggested， em prime on itself。

That is where the contradiction will happen。Select。Beta now be the encoding of emme。

During machine and prime。That is M prime is M beta。And ask the question。What is。

 what will emter do on itself。That's the。Oh。Question， which will lead to。A big insight。Okay。

 what does this steering machine beta。Do on itself。So， beta on beta。Su。😔，If。Enm bitter on bitter。Now。

 remember that。There is no problem in Mme halting it always halt。No matter what input alpha is。

It always holds。 So maybe I should write that。There is no issue about M prime not halting on some inputs it always will halt because it either send outputs it halts and either outputs 0 or 1。

There is no infinite loop issue in em。So M beta beta can have only two possibilities either it halls give you。

Gives you one， and it gives you。0， that is the only possibilities of what does it mean when it halt and give you one。

So， then。It means that。Either。M 01。Beta， bitterta。Is 0。But I mean。

 basically saying that either m beta on beta does not。Ht。

Which will obviously contradict that mta which ties 1。So this is actually coming from step one。

They think of this as step 1 case。That is one place where you can get output1。

But that happens only when m0 beta beta is 0。Which is。Which gives a contradiction。Can't hold。

So that leads to a contradiction。It because we are in the case where m beta beta value is1。

 So obviously it halted。 So it cannot be that you got output one in step  one。Let's go to step 2。So。

 all。A。And beta， beta holes。But in step 2 getting an answer one output1 means that。

The value of m beta beta has to be。0。So which again is a contradiction because we are in the case where mta beta is 1。

 right？Hence M beta beta cannot be1。That is what we have reduceduced。

So now let's go to the other case。So， this means that。M beta beta has to be 0。

That's the only case left。In this case。Output 0。In the in these two steps， when do you get output0。

 it is only possible in step 2。And which means that m beta beta should be。1。

Which is also a contradiction， because。We have deduced that mwta is 0。Right， so。

So you have to maybe look at this proof many times before you completely understand what just happened。

So， what happened is we assume that M0 exists halting problem solution exists。From that。

 we designed this em， which kind of。嗯。Nicgateates the answer。

And also takes care of the infinite loop。 so that em prime is。It always holds。

And then we are asking what happens when M is given M itself。

And there we have ruled out all the cases， which means that m prime cannot exist。

 which means that m0 cannot exist。That's approved by contradiction。So， this means that M prime。

Can't exist。Which means that。M0 can't exist。Right， so we had assumed that M0 exists， so。

We have now deduced that halt is uncomputable。Next， so this is a。

This is a first breakthrough in insight that。Once we have formalized machines。

Then machines cannot understand machines。Right， at least machines cannot。I mean。

 even machines cannot even decide whether other machines will stop。Like that。That is an uncomputable。

Question in that。Model of machines。And since we。Believe that theoryuring machines are the only possible machines。

So hall just cannot be computed。Ever， by any model。So this proof technique is called。

Dagagonization argument。Why is that。What is the diagonal here。Okay， so for to see that。

 draw this picture。So list your tuuring machines， M alpha here。

The rows basically are indexed by curing machines。And the columns are indexed by。Inputex。

Okay so both obviously rows and columns are indexed by strings。And。Now， you ask。

For this row row string。Will you feel the answers。Wde。Column string being used as input。

And what this。During machine M prime is doing it is negating the answer right。It's actually。

Working here。It is negating the answer of what m alpha alpha and alpha right so alpha comma alpha is referring to the first diagonal entry。

You can think like that。 then for the second string。Is the second diagonal entry alpha alpha。Then。

 third。Is the third alpha。actingcing on the third alpha input。Has input and so on。Okay。

 so this is the diagonal being talked about。So， this is the di。So。

 the machine m0 that we define or M prime that we define using M0。

It' is actually only looking at the diagonal。These values and negating it。嗯。

So once you negate the diagonal， then you get。So， that is what then leads you to contradiction because now when if this m beta existed。

I mean， when m beta， you act on。You simulate mta and beta。嗯。That will give you a contradiction。Okay。

 so it was all about this。These diagonal entries。If you have negated all of them， then。

That gives you the contradiction。There cannot be a tuuring machine。嗯。In the ruindices。

RightBecause rh indices any index that you look at。It will。Be unable to give you the right answer。

So beta cannot come here， for example。M beta cannot exist here。Right， because when you see。

Its answer here。You will see that。 It's negated。Okay， so this is the diagonization technique。

 it is actually not the first time that tu used it。I mean。

 definitely in computation it was the first time， but in math。In other。

Places this idea has had appeared。So， let me just write that。But during machine is designed。

That disagrees。With M alpha Al for all alpha。So that during machine M beta cannot exist。That was the。

Contradiction。So this technique well see in this course as well， which is why I have。

Given you this recap。And before this， it was used in other math results。So， this technique was used。

In other， in earlier。Foundational。So what were those foundational results。So。First is。

 and I think this is the very first where this technique was invented by cantor。So， cans proof of。

The uncountability of reals。Uncountability of reals。Canne 1891。So what is this result。

 this says that the set of reels they are in byject。With subsets of natural numbers。I mean。

 this you already know， you can write any real。As basically looking like a subset of natural numbers。

Can just think about the。Reals between 0 to 1。 So they are。In decimal representation。

 you can think of。The binary string appearing after the disem point。

And that is a subset of that defines a subset of natural numbers by their positions of one。诶。

And what canter showed is。The following that this is。Strictly bigger than。The set of natural numbers。

 there is no bijection。 Okay， so there is a。There cannot be a bijection between natural numbers and the set of natural numbers。

 the set of sets of natural numbers or set of subsets of natural numbers。

So real is strictly bigger then。Natural numbers。In fact， you can also put rationals here。

And because rationals are in bijection with natural numbers。Okay， so reals are strictly bigger then。

Rationals， though， obviously both are infinite sets。

 So Canantter was the first one who actually can compare two infinities。K by his， his argument。

 So maybe try to prove this by the dagonization trick。As the homework exc。

Second is Russell's paradox。Slightly later。So Russell's paradox。

 she says that certain sets don't exist。Okay， so you， for example， you cannot say define let。

SPS set that contains。Everything。😔，Okay， so such definitions。He showed they don't make sense。

And the way he showed it is by showing that the set。W。Which contains x's。

Says that x is not contained in x。This doesn't exist。Okay， so this also you can do so。

You can prove it using the dilation trick。As an exercise。So。

 although I have written the definition here， but this definition actually doesn't make sense。

Which is the paradox。Third is。Probably the most famous one。Cudles。Incompleteness， theorem。

Which came much later。Around the same time as stirring， actually。So incompleteness theorems。

 theorem says that。There are actually statements in math which you cannot prove or disprove。

Its just impossible。 So there exist unprovvable statements。

OkaySo unprovable means that you can write down or Gu wrote down a statement which。

You cannot prove it's true， it cannot prove it's false。the true or false cannot be decided。So。

 their truth is。Uncidable。Okay， this tie is actually very well with also halting problem。嗯。Yeah。

 so some of the。I mean， really big。Of。Big steps in math。Also philosophically speaking。

 they actually involved。The dagonization argument。Okay， so enough of this。

 so now we move on to more complexity things。Only looking at problems that are computable。

 So for that。Let me define the notion of reduction how to compare problems that are computable。嗯。

Let's say。In an equilibrium。So， a function。If。😔，Can be shown oncomputable。Okay。

 we are still in this possibly uncomputability regime So okay。

 how can you show other functions to be uncomputable or other problems to be uncomputable。

That you can do but if you can， you will get that if you can reduce halting problem to your problem。

RightSo that because once you have a reduction。Obviously， your problem cannot be。

Easy because if it if if it was easy， then you will also solve halting problems。

 So your problem is also hard。That's the idea of reduction。

So a function can be shown uncomputable by。Reducing it。D。By reducing。So， notice the direction。

By reducing。Ht。😔，With。Okay， there's the correct direction。

That would mean that F is also uncomputable。 It is very hard。So， that is design。A computable。

Function F prime。Such that， for all inputs。Hall tox is the same as。

So what will a frame do a frame will basically modify the inputex。And then， apply if。Okay。

 so reduction is nothing but a composition。Okay， by where a computable function is involved that you have to design。

So this F prime is the key thing。This we have to design， this is called the reduction。

Bch field basically when you actually wanted to solve halt。On x。

 so instead you modify x and give it to F。And that will solve whole。 Okay， so this。Third function。

 this is called reduction if this exists， then it shows that your problem is harder。And。

We write this as。Ht。😔，Reduces to F。Duringing reduces。Okay， there is a tu reduction。

And this means that f is also uncomputable， so we will make it more precise for complexity。

The next class。🎼Yeah。

![](img/a18899a7f2546726c92bedeb80f8f128_2.png)

![](img/a18899a7f2546726c92bedeb80f8f128_3.png)