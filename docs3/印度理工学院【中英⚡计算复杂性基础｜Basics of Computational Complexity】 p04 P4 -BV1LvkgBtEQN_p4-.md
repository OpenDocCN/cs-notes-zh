# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p04 P4 -BV1LvkgBtEQN_p4-

![](img/1cc4864f854bafbdf2323e07a3d45729_0.png)

We are trying to compute parity。W and see the definition of during machine in action。

So read a bit of X。Basically， it's a。Incremental algorithm。The roughly。

 the Teaing machine proceeds incrementally。So it will read bit by bit。

So say you have read the first i bits when you read the i plus 18 bit。Either it will be 0 or one。

 so if it is 0， you don't change your current parity。

 leave it unchanged or you read one and then you flip the parity current parity right that is the correct thing to do。

Because， remember。1 plus 1 is 0。While 1 plus0 is 1。Right， so when you see a one， you have to flip。

When you see a0， then you。Don't flip。Okay， third step is continue till。

You reach the blank cell in the input tape。😔，So continue till。Input cell。Becomes blank。

It blank means that the input is over。So you keep repeating this loop。

It is just a simple loop and the head keeps on moving forward on the input tape。

And the states are only。Two more。 so obviously start finishes there， but you also have。

You can think of as parity0 state， even state or state。Greatai， so。And then。

Whatever state you are in。When the clearing machine holds， that's the answer。So， right。0 or1。

As the output。Based on the state。On the current state。And then， move to finish。

So that is how the Tearing machine would。scan the。Peps and change the state。Right。

 so very simple algorithms you can see are clearly implementable， sim level by a Qing machine。And。

 in fact。We can also draw this as a picture。So。You have the start state。

 and you have the finished state。Its two vertices， and you have。Let's say the even state。

And the odd state。As vertices。Noao。😔，Think of the vertices as the states and。Edges as transition。

Function values。 So when should trans， when would the transition functions say that move from state Q S to Q even。

Q even corresponds to current parity0， right， So if you see a 0。Fex is the first0。

 Then you move to Q even。Or even in this case， so。You are on the start。A configuration。

 And from there。You will move， too。I mean， you will not change the。Cells， each of them will remain。

Start symbols， but。On on the input， you will move right。Don't move on the。Work tape， right。 So this。

 the only information here is actually are this right movement and the input。Deep。

And the other information is that。嗯。After start， you have moved to。The parity 0 state。

And now on the when you move on the right， now the input head sees the first bit。based on that bit。

It has to take an action。So what is the action。So if this bit is 0。They don't change。Anything。

 just keep moving right。Keep this so read the second bit。

State doesn't change because0 means parity still is 0。On the other hand， if you you see。Wen。

Right then。Keep moving， right。That's fine， but the state has to now flip， so it goes to odd。

Because first pick being one means。Paity has now become one。Now， in odd， there is。

If you are in odd state at some point of time， then again。Looking at0。

 you will remain in the odd state。And you keep moving right on the input tape because you want to move to the next bit input bit。

 right？🎼And it seems that the workta is not of any use work tape。

 the head is always on the start symbol， right？So this doesn't even need the work tape， actually。

And yeah， the reverses。If you see a one。If you see a one， then from all you go to even。

So this is kind of the loop even toward。O to even even toward whenever you see one。

 if you keep seeing one， you keep moving in this loop。 if you keep seeing 0。

Then you are at the same state， So even to even。Or what to。And when will everything come to an end。

 when will you reach the finish straight。So， that is。When you see blank。So at that blank。

 if you are if you are at even state， then at that blank you write the output 0。

And there is no need to move right anymore。Sim。A similar idea when you are at odd， you write one。

Okay， so this is the。State diagram of the tuuring machine。 So above is the。Steps in words。

And below is the state diagram which is telling you in a compact picture。

 it tells you what the transition function is via the edges。What the states are。

Where are the vertices。And。You can。Dri run the whole execution of your algorithm。

 So this is the state diagram。Okay， so。So， you can see that even a simple algorithm。

 almost a trivial algorithm。嗯。It takes a while to write down the describe the Tring machine and describe the computation。

Okay， so although the definition is easy， there is a lot of notation。

So it it gets quite tedious to describe the Tring machine， but still you have to keep this in mind。

Because。This is how everything is formalized。 Every algorithm ultimately looks like this。Okay。So。

 the state diagram。Describes the transition function。Describes Dlta。With the Nords being。State cube。

And D Hs specify your transition。SoSo nodes are streets， edges are transition。States。

You will see these big vertices。But the rest of the information you will see on the edges。And。

In the in this example you can see that work tape was not used and also you can see that the output is written at the last bit。

At the end of the input tape。So， in the example。Work tape wasn't。Used an input bit。 sorry。

 output bit。Output bit is at the end of。Input tip。Right this we saw in the state diagram that。

When the transition happens from Q even to Q F。We wrote  zero。At the first blank you saw。

 So that is the end of the input tape and。Smit analogous thing for Q or to Q F transition。

 So one property that you can see。Is that。The size of the state diagram。

What does it signify practically。Read a bigger state diagram means what。So。

 bigger state diagram means。A bigger program。Right， so size of the state diagram。

Is kind of proportional， too。Size of the。C program。Letxi。😔，Simulating this algorithm。

Right that is the kind of the physical interpretation， if you will。Of the state diagram。

 bigger state diagram means that。Your C program will be that much bigger。Because in the C program。

 you have to take care of。These steps， it is kind of a flow chart that you are implementing in the C program。

So， as though if there are more states， then you have to maintain more variables in your C program and if there are more edges。

Then you have to implement more if than else， conditions。Okay。There'll be more loops。So。

4 or while loops。So yeah， the program is fixed。Irrespective of how long the input is。Right。

 that's an important thing to remember。This size。Is independent of。

RightSo once you have written the program C program， it doesn't matter what the input is or。

Your input can be arbitrarily large。So in the future， when there will be a bigger computer。

 bigger hard disk。You can it the same program can run with bigger inputs。

RightSo so this is something that you have to appreciate at this point。

That the finite control and the state diagram transition function， these things can handle any。

I mean， you have to design them so that they can handle any length input。Okay。

 so x is can be infinitely arbitrarily long， so。This is why you need in the tape to be。Infinite。

Although the program， the control is finite。Okay， so that was a quick。Recap of things you learn in。

Through you of computation。And now， let us get down to。Counting the resources。Bounding them。

So we start with time complexity。Of a tuuring machine。So， let。If。😔，From sts to themselves。

FB function from string to strings to strings。An MB Turing machine。Computing F。L。DV function。Okay。

 so F is what you want to compute。 you computed by during machine M。And T is the function that。

I'll use。To denote time complexity。So what is that。So， we see。嗯。That M computes F。In PM end time。If。

For all input strings x。M Hol。After。At most， T of X。T length of x。

 So this bar notation means length of x。 how many bits there are in x。In T of x steps。Obviously。

 just halting is not enough。 it should also give the correct answer so。And outputs。F of x。

So it should halt and you should give the correct output in。呃。

Number of steps of function of this function T of the length。Okay。

 so this is important we want to capture time complexity as a function of the input string。

Why is that well because the input string can be arbitraryarily low。So。

 we cannot keep track of for which string how much time it will take。Okay。

 there are just infinitely many strings。So we actually want to focus on。

 We want to get a ballpark idea。A ballpark number， in this case， function T。Which tells you， okay。

 how good or bad that youring machine is。SoSo we have defined。M computes F in T time。Similarly。

You can define。That。What is the meaning of the expression M computes f。In S of end space。Yeah。

 so this phrase M computes F in S O S of n space， this will be。How many。

Work tape cells were utilized。So for example， in the previous instant example of parity computation。

Work tape was not used at all。Only one bit of the input。Tap was used。

 so it was actually constant complexity， space complexity。

And what was the time complexity of parity computation？

So the time that it took was proportional to the length of the input。Right， so。We can write that。

Sup for parity， we saw。That。P of N was。 time was。Around n。Okay， the length of x that many。

Steps there。And the space complexity was。Just one。No work tapepe cell was used and。

One output B bit was written， so。So that is what happened in the。This example， tuuring machine。Okay。

 now we also don't want to be too precise with T and S functions。 We want to again， get a ballpark。

Estimate。For these functions， for that， we will formalize。Asymptootics。

So what is asymptotic notation。So， let FG B functions。I short。Shortten function to F N。 Okay。

 so FG B functions。From。Natural numbers， to positive wheels。Or non negative reals。So， big O notation。

Is like this。Okay， writing f equal to biggo of G， What does this mean。Roughly。

 this means that f is less than equal to G， but up too constant multiple。So， if。They exist。

 constants。Xi。😔，N 0， such that。For all n greater than equal to n0。F is。Less than equal to， sorry。

F of n is less than equal to c times g of n。So note that there is there is。

 there are two relaxations here。 First is that。F can be a multiple of G。But it has to be constant C。

Second relaxation is that this inequality may start to hold after a while。Okay， this ends up to n0。

 it may not hold。Remember that。But beyond n0， it is always true， right So after a while。

F is bounded by G up to a constant C。 This is what。F equal to big means big omega。So big。

 if you write F equal to big omega。That's， basically。The opposite of first line， so。

You will write this， if。G is equal to big of F。Okay， so if g is big of f， basically this。

 you are saying that f is greater than equal to G。Up to a consency。Okay。So biggo is an upper bound。

Big omega is。A lower bound。Then， there is theta。If equal to theta g。

Which is if both of them are true。So you have both upper and lower bounds。 Okay。

 G is less than equal to some constant times F F is less than equal to some constant times g。

So FNG are practically the same that is what Theta is saying。So， theta is a good bound。

 okay ideally you want theta。You want this relationship that two things are equal。For Biggo。

 there is a small。What is that。嗯。So， small low is。This idea that F is strictly smaller than G。

So it's not constant multiple， but I mean， this is like saying。So in the biggo case。

 f by g was like a constant。In smaller case， F by G is like 0。O， by Z1s to 0。

That's a simple way to put it。As ns to infinity f by g G becomes much larger than F。

And key is becoming larger and larger。 So the ratio is 0。Similarly， small omega。

So small omega is opposite of this。So if G is smaller of F。Right， so instead of， I mean。

 small is saying that f is significantly smaller than G。

 small omega is saying that f is significantly。larger든지지。And finally， there is。Also， an o tilda。

What's that。So， F is O tilda。Zi。😔，If。😔，This is like Biggo， but here the constant multiple is relaxed。

It is relaxed to smaller functions of G。So。If。F is less than equal to。G times some smaller functions。

 So we picked log G。Okay， so G log G is。Britain has O Daji， or you may even allow。Constant powers。

SoSo log G is much smaller than G。 And we are just allowing constant powers of that。

So you don't expect this to be too large。Okay， so although f could be larger than G， it can。

 it is not much larger。 That's the point。And just symmetric to this， you can have。嗯。오미가 덜더。

So you write omega tilde G。😔，If。G is。If g is less than equal to。Soty。😔，If g is equal to big tillde。

If。Okay， so and so on you can。Toefine such functions。 This is。

The idea of all these functions is the same， which is。Understand the asymptootics。O。Let's set。

 time complexity。Okay， so if。You are solving a problem by one tuing machine that takes F time。

Other takes， other tuuring machine， other algorithm takes G time。How do you compare the。Goodness。

Of these two algorithms。 So you basically will。Use an algorithm。 that is。

That has a smaller time complexity， right， So you will want。If equal to small low of G。

That algorithm will be better for you because F time complexity is much smaller than g for larger inputs。

And if f is equal to theta g， then you will not care much。Although in practice。

 the constants may be important。But in theory， F theta G。

 F E equal do thetagy means that the it's only a constant difference。

 So time complexity is kind of the same。 So mathematically the。The algorithms are kind of the same。

So this is the asymptootics we use。And we can see some examples next time。🎼。



![](img/1cc4864f854bafbdf2323e07a3d45729_2.png)