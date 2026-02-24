# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P8：lecture 8.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/be20867f8bd456f48459895c984dd9b5_0.png)

Welcome， welcome everyone， good to see you all today we'll cover the last piece in this section on linear algebraic algorithms。

So we started talking about tensor last class， tensors。Good。So let me just。Recall what we said。

 you know， we said let's look at three dimensional tensors or but you know a lot of things that we say also applies to higher dimensional tensors and so you have like a three dimension layer of numbers。

Which will call a tensor， and it has three modes。 And if you have a higher dimensional1 higher。

Atensor with four modes is one， which is a four dimensional letter of numbers。

 so there's three mores and just like a matrix can be visualized either as a。

Polynomial in two variables。Or a map that takes a vector and gives out a vector as a linear transformation or a bilinear form。

嗯。Similarly， a tensor， you can， they naturally think arise as。Polynomial in three variables。

 for instance， if you have a polynomial in three variables， let's say for simplicity， X， Y， Z。

 which all which have n coordinates each x1 through xN， y1 through YN and Z1 through ZN。

Then a multiline polynomial。Is a submission TI JK X I y Z Ek。

 so that's a natural way in which a tensor arises， but you could also think about tensors in different ways in which you can think of it as a map that takes two vectors and produces one vector or takes one vector。

 produces two vectors and so on。是。And finally， we said an important place where tensors naturally shows up is in data。

 if you have data like samples from some distribution， let's say distribution B over R to the end。

 the mean itself is a vector， the covariance is a matrix， as we all know it's the。

Sort of the pairwise correlations and now we can look at triple correlations these are this would give you a degree three moments as you should call it that would be three dimensional tensor Okay。

 so that's basically how you know tensors arise。And so just like matrices。

 you would want to have similar notions for tensors， right？

We'll see which of those work out well and which don't。So firstly， for matrices。A natural。

 very important notion is that of a rank。And you have a low rank and high rank and things like that。

So what is rank？Well， I guess there are many definitions for a matrix rank。

 but here is one possible definition。Let's just define rank1 matrices。So rank one matrix。

Is something that looks like。Colum vector。Multiply with the ro vectoror。So。

You can write it as UV transpose。Okay， so that's a rank1 matrix， so the IJ entry of this matrix。

Is just sorry， the I entry of this is just the product， right， U we transpose。I J is just U I b。

Right so that's a rank one matrix and now with that we have a definition of a rank one matrix we can talk about a rank of a general matrix right so here's a definition。

You could say that。A matrixtri。えランケ。The matrix M is rank K if m can be written as sum or I equal to1 through k。

You。Let me use different notation。So if you can write it as some more K rank one matrices。

MmI rank of MI is one。Okay the sum of k rank1 way， you could say that's rank K， but of again。

 I have to。Say that this is rank utmost K。Really， if you want to define rank K properly。

 you should say a matrix M is rank K if you can write as sum of rank K rank one matrices and you cannot write it as a sum of。

嗯。嗯。嗯。K minus-1 rank 1 matrices。Then it's rank， so it's the minimum number of rank1 matrices that you need to add to make up this rank matrix。

So that's a natural definition of rank。I mean， of course， in this case。嗯。There are other definitions。

 right， so you can look at the column space of M。The vector space spanned by the columns and you could ask what is the dimension of the column space of n or the dimension of the row space of hand。

 all of them are the same value， which is the rank of the matrix。Okay， so。Okay。

 but let's stick to this is a very concrete definition。

 so in particular you know just to make it concrete so really this sum looks like sum over i equal to1 through k UI VI transpose。

ok 我想。Yeah， but's it。So。So now we want to do it for tensors。Defined rank for tensors。

 So just some notation is that we will。Red definedfined tensor product， right？ So U tensor we。

Tensor W。Okay， this is， let's say U VWR。N dimensional vectors。All of those are in R to the end。

U VW or in r to the M， then U tensor v tensor W is basically what you think it's the three dimensional array which has entries UI Vj ZK UI VjWK。

Like， it's the。It's sort of the。3 dimensional ladder。I don' I'm doing this with entries being UI。

 VJWK。O。So of course， the two dimensional version of this is utens are raised。

 nothing but the same as UVv transpose。RightAnd。Of course。

 the same thing you you similarly you can define tensor product of any number of vectors。嗯。Allright。

Okay， so now what is rank1 matrix rank1 tensor， it's exactly what wed think rank1 tensor is just really U tensor V tensor W。

Ford。You will take three vectors， and take the。At tensor product， that's a rank one tensor。 Okay。

 so now we can define。Rnk。Offer ten。It iss the smallest gate。Sas that。

T is equal to some of a bunch of rankqu tensors and write it as UI tensor， V tensor， W。对。

And I걸 do want。Yes it's a natural definition。Okay， so how does this definition fare？Unfortunately。

So firstly right and firstly there's many ways in which this definition is not so nice。

 not as nice as a matrix rank， but let's see what what it is so firstly。你。

What is the maximum rank of a tensor？Offfer end， end by end。And end by end by end， tenor。

Can anyone guess？I mean， we didn order of magnitude。And cubed。

N cube right right N cube would be the real upper bound。Yeah。

But you could do you could try to do parameter counting。So if you think about number of parameters。

 so an end by end by end tensor has N cube numbers in it N cube parameters to specify and rank rank。

Kate answerr has。You know， K times。3 n squared，3 n。R K times 3 n numbers needed。Right。

 because U V W at K times3 in number。 So so you can imagine that the rank can K and go all the way up to order n squared。

 And yes， that's what will happen。 So imagine rank of N by and by in tensor is。

It can be as large as in squared。嗯。Yeah。Sorry just a question so I guess in general is it is it like the dimension minus one yeah in general it could be the dimension minus one。

That's sorry yeah。So so already you see that the number is yeah going quite higher than usual。

 but actually this this rank for tensor it behaves quite badly than the usual rank So here like one thing is。

嗯。The rank。Depends on。Whether you are working over rails or complex numbers。So meaning for a matrix。

Let's I just give you a real matrix。Its rank is independent of whether I allow you to use real or complex numbers for the vectors UN B。

RightBut for tensors。Depending on whether I allow you to use real or complex numbers。

In the vectors Uv W。The value of rank can differ。嗯。Clearly， if I allow you complex numbers。

 the rank should go down because I'm allowing more possibilities for UBW and there are tensors for which that happens。

Okay， and then the， I guess that's okay， mildly annoying but but whats sexy is somewhat even more annoying is that。

嗯。So for matrices。嗯。The following fact is true for matrices。嗯。If I have a sequence of rank rank。

Low rank matrices， M1， M2。Right， a sequence of。Ranque matrices。Okay， if I take the limit。

The limit is also rank K matrix。If it exists。Okay， I mean， concretely for。For us， computationally。

 what this means is if I give you a matrix and ask you what its rank is。It's if it' if its rank is k。

 then。you can't have arbitrarily good approximations whose rank is lower。Whereas for tensors。

 this is not no longer true， as in the axis tensors。第。Such that rank of tea is high。Like。

 I think it's even， okay， I don't have it here。 It's something high。

 like like something like N something， right， but。something系 large。But。For every。

Like you can approximate， but T is very， very close to a lower rank tensor。But you know。

 for every epsilon， there exists some tensor T T prime。Such the rank of T is low。And t minus t prime。

I is smaller than Epsilon alternate in terms of sequences。

 there are sequences of tensors says that the limit is high rank。

 but everything on the way is low rank。RightAnd that's bad because it just means that your notion of a rank is not robust。

 a tensor can be high rank， but。You can get arbitrarily good approximations which are low rank and it is。

little bit。明。OkayAnd finally， as you can suspect， you know， since it's not behaving nicely。

 like most quantities， it's NP hard to compute。The rank of a tensor is NPhar compute and it's actually even worse。

诶。I mean， clearly， just by parameter counting， we said， you know， just by parameter counting。

 we said the rank of a tensor should be n squared， right？嗯。And if you pick a random tensor。

 you should expect its rank to be n square because it's。Like you don't have any structure。

 this is the largest number of parameters you need to be n squared。But we cannot， we are unable to。

Construct any explicit tensor。Whose rank is more than。And significantly more than n。

I think the best explicit answeror for which like。We can prove a lower born in the rank is something like three times n。

What I mean by explicit is if you ask me for a rank n matrix。

 I can just show you the identity matrix or I can show you the Hadamard matrix and say， okay， look。

 this has rank n。Or the Fourier transform matrix rank n， okay。

 almost every tensor has rank n squared。But we can't explicitly write down any tensor whose rank is。

More than an like more than a linear。Yeah， so it's kind of a big little fairly open question for a long time now。

It's related to circuit log bounds and things like that constructing explicit tenses with high rank is。

柜台。Oh yes， thanks。Rannk of T prime is small， but rank of T is large。Okay， so so much for rank。

 it's kind of not so well behaved， as we can see， but you know。你。😊。

There are some other things which are related which kind of behave much more nicely and more amenable to algorithms。

So here's something you could hope for is e decomposition。Okay， so if I assume。Something special。

 so what is the thing， So if I have a matrix M。You can think of it as you can write。

 let's say symmetric matrix or real symmetric matrix。Okay。

 then you can write M as sum over lambmbda I。VI VI transpose。Where。

Each these each VI is an eigenvalue is an eigenvector。Right。Eigenvector with eigenvalue lambda。

And moreover， these Vs are autonormal。I going let's say。어떻거나널 뒤。Okay。

 so and you can do this efficiently。Okay， so let's say I give you a tensor。Which looks like this。

 So it's somewhat Im assuming asking for a lot， so suppose。A tenor。Looks like。Atogonal vectors。Okay。

 so AI Tensor 3I is just short shorthand for this is just shorthand for AI tensor， AI tensor AI。Okay。

Okay， and。Yeah。Right， so okay， so now suppose I give you a tensor like this， you could ask。Of course。

 now because I'm saying that EI is are orthogonl vectors， I cannot have n squared of them。

 I can only have utmost n of them。Right。Just because I said they're orthotgon。

They can only have any of them。 And now the question is， can you recover。え。

Can you recover AI and what else can you say about this situation？

This actually one like a very nice situation to be firstly your tensor is super low rank。

Its rank is n instead of n squared less than n， and you have thisocgonality。

Here it can recover AI in many different ways。 Okay， so let me just show。

Right let's just see one way to recover A eye so。一是先的。So。ok。So you have these tea it is。エ some or来。

AI tensor， AI tensor， AI。ok， now诶。Let's do the following， Let's。诶。

Take this tensor and apply a vector to one of the modes。So what I mean is。Let's look at。The。诶。

So let's pick， pick some random。big。Pick a random。vectorctor g。

Just speak random vector and now apply this vector to one of the modes to create so。Yeah， okay。

 so I don't have a good notation for this， but let me write。T of G come dot， come dot。

Okay create this tensor， new tensor。Which is somewhere or i equal to1 through n。AI in a product G。

Times AI， AI transpose。So let me just write AI tensor AI so that it's clear。It's a matrix。

And how do you how do you essentially get this matrix， you have a three tensor， right。

 which is like a three dimensional array of numbers applying。You know。

 G to one of its modes is to take the slices of this。You have n slices along one direction。

Take a linear combination of the slices with the coefficients G1 through gM。You get a matrix right。

 so that's what I mean by applying。Applying G to one of the mors。

And if you apply G to one of the modes， what you end up with is this matrix。

 AI in a pro G in a pro times AI it tensor AI。几。This is something you can do。Do。Denss， right。

 you can。嗯。Apply vectors to any subset of modes， for instance。

 if I take a tensor the same tensor T and apply G to the first mode。

 don't apply anything to the second mode and apply H to the third mode。

 then I end up with the vector which looks oh yeah I guess I end up with a vector which looks like AI in a product G tensor well I don't need tens it's a number。

Dot AI。Dot。Yeah。In a appropriate。So you just get this vector。Right， so it's a。嗯。

It's this thing where you can take cleaner combinations of slices of these things and get new slices。

 okay， so that's a very simple operation。So okay so now this is nice so what did we get here we got a matrix and for matrices we know we can do many things we can compute eigenvectors。

 eigenvalues and so on so。So let's just look at this matrix now that we have， so we have this matrix。

And you can see that this matrix。边の。Its eigenvectors are。Eigenvectors are。Bs。And the eigenvalues are。

嗯。嗯。Eigenvalue are I guess what you。Well， I mean， if you normalize appropriately， it's AI inapply。系啊。

So why is that true？I mean， it's just if you take this matrix and hit it with。Any AI？Okay。

 it's the same as。决定。So basicallyI AI transor AI is the same as AI AI transpose。Right， and。So。

You know， you get。Let me just do it anyway。If I multiply this matrix by AI， I get， let me do AJ。

 AJ and AI。J equal to 1 through M。Cl here with the I， you know， when J not equal to I。I get0。

And for J equal to I。I'll get。EI in a product G time C I。Times E in the product of EI， which is。

I guess yeah， that's where good。That's what you get for J equal not equal j equal to y。

 and so when you sum it up over all J， you'll just get a multiple of AI。ok。Is it clear。It's this。

I guess this is sort of the like in the conception it guess the want to。It's not stated explicitly。

 but this is sort of the book。Only thing to organism， but the most important thing about tensors。

That you want to internalize that。You know， they are really three dimensionary of numbers， but。

They have linear algebraic structure on there， you can apply vectors might take linear combinations of the modes。

 also linear combinations of the slices， right。And things like that， right， you know， like the more。

 like for example， if I give you。Weectctor T or a tensor T。

Right and I give you three and let's say this is in end by N by N tensor。

If I give you three matrices， A，B C。Which are in R to the end by N。The end by N matrices。

You can apply ABC to the tensor。I mean， I don't have a good notation for this， but ABC。

 you can apply to the tensor on the three modes。Separately。What that means is。Like applying a matrix。

To one of the modes is like taking linear combinations of the slices to create a newtensor and then applying a matrix in the other mode is creates linear combinations of the other and you know ABC is like you apply this linear combination of the slices。

 then you apply this linear combination then you apply the other third linear combination of the slices。

And in different modes， in different directions， either one in this way， one in this way。

 one in this way。Okay and that's that's you know， we can do that to atensor right and sort of this is a little bit of a tricky thing to internalize。

I sort of I can prove if but I don't have a good mental model of this， these things。

 it doesn't matter what order you do this， right？So。

You can take the linear combination of you can take a specific linear combination of the row of the vertical slices。

 then take another linear combination of the horizontal slices or you can do it in the it can interchange the order it doesn't you still get the same time so anyway so this is just a basic okay so so all right so in this case in this very special case you can actually recover the vectors AI okay and it was very easy just。

Use eigen way to recover eigenvalue present eigenvalues and the only thing you sort of had to argue or say is that well the eigenvalues you see theyre random numbers depending on your choice of G。

And you know， when you take random numbers， they're going to be distinct。Right。

 so your eigenvalues will be distinct if the eigenvalues are distinct， you can。

Recover all the eigenvectors explicitly。Right。When matrices。

 the only reason you won't be able to record an eigenvector is if two eigenvalues coincide。

 but that's never going to happen here because if your eigenvectors are eigenvalues are AI in a product G。

 they'll never never happen。Yeah。Okay， so that's。That's okay。

 so that's good we can so there's this identity decomposition and you。

If the mattensor has an eigeniccom like this， you can recover it actually in this case there are many other things that are true。

 which are all similar to what's true for matrices。就。So like let me write it， so suppose I define。

T x comma x comma x。This is this function。Well， that's the polynomial， right， some more T I， JK， X I。

 X， J， Xk。And if t is actually equal to some over AI tensor 3， this will be equal to some。

e i g sorry。AI in in a products。Hhole cube。ok， so诶 that's right。if t has an eiccomposition like this。

 then the corresponding polynomial looks like a sum of cubes in this basis。

 it just looks like a sum of cubes and what is true about this is that the theorem is that if I look at this function。

 t of x comma x comma x。嗯。Then it maximizes。Firstly， the maximizes。On the unit ball。啊。These vectors。

 even through A。Okay， so this is just like the maximizes for a quadratic function are the eigenvectors。

系 the the。The largest， if I maximize asymmetric quadratic function。

 I recover the largest eigen vectorctor， similarly if I recover if I maximize a form like this where the AI is are orthogonal。

It's maximize all the vectors，13A。Okay。Sorry， not maximizers， local maxima。Local maximum。

Or even three。These are the only local maxima， so if you just run some sort of gradient descent on this function。

 the function is not convex， but in a sense， the only place you'll get stuck at are even through AN。

So you will recover one of the AIs if if you just run gradient as on this function。

Which is nice because that's sort of essentially what happens even at the。

I matrices right if you maximize the function record one of the eigenvectors similarly you can do that here and just like matrices there's a power method。

嗰啲咁。You can run there's an analog of the power method here。嘅啊。And。What else this？Yeah， I mean。

 this is sort of the only。Yeah， yeah， let's， let's， let's， yeah。It's one。

 so this is our only property。😔，嗯。So in some sense， if you had an eigen decomposition like this。

 where everything was orthogonal。I assumed that AIs are orthogonal vectors， in that case it's very。

 very easy， there are multiple ways to recover the AIs。Okay。Professor。

 I had a quick question on this page。So can you explain how the eigenvalues are AI？

Dot G if at the bottom， it says like right yeah， no， it like sorry the aggregatevalue actually。

No yeah， sorry it's not exactly that if AI is are unit vectors。

 then I canvalue that Ienvalue AI dot G， but if AI are not unit vectors。

 then you'll pick up another AI AI。Like the something with the length of AI but the right so you'll pick up some number like some factor it's sort of the length of AI。

 I think like normal AI cube。I sir what you。嗯。Yeah。

Norm of V I cube is what you pick up This time norm of V IQ， but。But I guess yeah。

 I mean that's the normalization aspect of it， but the key point of which I want to say is that you know it's just that it's an eigenvector is sort of important for us。

 just that you get when I multiply by AI I recover something which is some lambda I times AI for some value of lambda I。

And once I have that like that is true here， like you see that this is a factor。

 I mean this is a vector you recover and you see that there's a factor times your original vector AI。

Theres a number and that's the only thing we want to know。

We really care about here in that there it's an eigenvector and the eigenvalue is somewhat of a random number so it'll be distinct if you pick a random G。

 it'll be a distinct number for A VI。professorfessor。Yeah， question about the tensorrink， so。呃。

If we generate tensor with random entries， wouldn' that be an explicit tensor with a rank n squared。

 oh yeah， I mean， if you generate a tensor with random entries， it will have rank n squared。诶。

It's not explicit。I guess I guess that's like that， I mean， explicit by explicit really mean。

I guess one of like two things， one is。It's not random and two you can certify that its rank is high。

And when that's the game with play explicit constructions right so let me I mean the when we say explicit construction we really usually mean something where。

It's not random。And。It， it has。The properties that you ask for。

It's sort of a general theme in more so in complexity theory than in algorithms。

 but also sometimes in algorithms， but more so in complexity theory that you know that there exists objects。

 like somebody proves that an object exists by some sort of a randomized procedure。

But an explicit construction is， can you actually produce that object？

can you actually have an efficient algorithm， deterministic algorithm to produce that object？So。Yeah。

 it's a bit related to the following fact。Suppose I prove to you that a random function。

Is hard to compute。Well， it's quite easy to prove just by parameter accounting and the total。

 you know， you can prove very easily that a random functionist needs。

Big circuits are very hard to compute。 Okay， that's fine， but that's not。

It's not really satisfactory because nobody really cares about random functions。

 what you really care about is proving that the TSP function is hard to compute。😊，Right。

 and so that's the difference between explicit and。Or randomo。对。

We know that there exist random objects which are complicated in that the rank is high。

 but we don't have an explicit object like a。Explicit， I mean。

 if it formally defined it you want a deterministic algorithm that generates the entries of the matrix。

Yeah， that's a clean way side， for example。So we want some sort of construction that's generalizable for all n right because if ns like equal to two we could just like pick some like small integers and probably show its rank rank n squared right that's right yeah that's right。

Yeah that is right， though I mean I should add on that note I should add that computing the rank of these tensors is very hard。

 I think just this on side note if I give you a three by three by three tensor。You know。

 in some sense， we don't have very good algorithms to compute its rank in particular。

There are research papers written in the last few years。

which prove upper and lower bounds and ranks of very specific tensors which are useful for matrix multiplication or something like okay。

 this is a specific three by three by three tensor you want to prove it's a lower bound rank and then oh it 17 or is it 23 right and there are papers which do that。

Because it's NP higher right so it's can't really compute rank and it has this property that the border rank well the approximate rank or the border rank。

I didn't define border rank， border rank is this quantity， which is。

If I let you approximate the tensor with a。嗯。By another tensor， what is the rank？

You we saw that approximating it can be rank can be high。

 although we can approximate by low rank by a low rank matrix， so anyways。

 it's quite hard to come calculate。不是。All right， so let's。Okay， so okay。

 that's about dragon decompositions。Let me move on to。Something。And a different。嗯。Actually， I。

Let me show a more general version of algorithm。Which sort of this is an old algorithm。

 it's called Nris algorithm。And we'll see we'll show you this algorithm and we'll immediately see an application of this。

 which is kind of nice there are lots of applications of this algorithm and the tensors in general。

 but we won't。Go through many of them just see one today。 So I have a right I have a tensor I'm for。

 you know， I'm just using for generality， it's an asymmetric tensor。Okay。

 and I have an input is a tensor， and I'm going to assume that the vectors v1 through VR。

Are linearly independent。So not really orthogonal but linearly independent。

 similarly the vectors W1 through WR are also linearly independent。Okay。

And then I'll assume that U1 through you are a distinct。Not I mean weaker than linear independent。

 but basically think of them for now just think of these as a fairly linear independent factors Now of course。

 your goal is to find find all of these U1 through U are V1 through VR。And W1 through WR。Okay， and。

Here's an algorithm。This is a fairly。啊。我两灯。So let's see， I should have used different letters。

 but okay， let's let me try to make this work。So the algorithm is quite similar to what we saw just now。

 so you have a three tensor。You first hit one of the。One of the sides。

 one of the modes with a vector random vector， So let's pick a random G。And。

Hit one of the modes with that。 So let's say I hit the。嗯。I hit the。First mode。Okay。

 so what would I end up with， I end up with。This matrix， Ui in a product G。Times。VI tensor， W。

I could do one through art。Okay， so this， you know， so now this looks like a。嗯。

A matrix with some rank decomposition like a low rank decomposition of a matrix。

 but it's just it's not theigen decompositions that we wanted like these Vs are not orthogontal。

But you know， I can do this again， right so I can pick another vector。Pick G prime or pick H。

 Let's just pick H。 And I define。Another matrix M2。Which is， again， I do the same thing。

So now I don't have。嗯。These are not eigiccompositions of the matrix。

 but they are linear combinations of the same sort of an object。

 so we can hope to recover UI V IW from this so here's what you can do。So。This M M1。Actually。

 let me call this Mg and MH because they come from G and H。MG is actually。You can write it as。

The following， you can write it as。A matrix V。Bg。W。Where we end。And similar， this is matrix V， D，HW。

 let me say what V and W are。

![](img/be20867f8bd456f48459895c984dd9b5_2.png)

![](img/be20867f8bd456f48459895c984dd9b5_3.png)

So。V is a matrix with V1 through Vn as it's。Columns Dg is a diagonal matrix with。U one dot g。

U i dot g。It's a diagonal matrix。And then W is a matrix with w1 through w。And as it's called。

 as it's rose。So that's this like Mg looks like this matrix。

And image looks basically like that except you change the diagonal matrix in the middle from Dg to DH。

 it's a different。And DG and DH have entries which are basically random random entries because Ui。

 G is like a just a random random entry so these entries are rank。Okay。

 so now we have these two matrices now， okay， M is Mg is V D GW and MH is V D G， DHW。Okay。

 so we are sort of close if we want to recover B and W。Right and it's quite easy from this point。

 The point is， let's just look at。If I look at Mg。MH inverse。Okay， let's look at Mg image inverse。

 what do I get I get V。D，H。W。Times。W inverse， Dg inverse。Veners。所系唔水人。I switched the engineer edge。

ok。And now you know， WW inverse cancer， I end up with V DGDH inverse。

 this is a diagonal matrix in the middle。And then weless。Okay。And。When you have any such matrix。

Like here's a sort of facility silly observation， the observation is if you have a matrix M which is equal to some PDP inverse。

For some invertible matrix P。Then。Basically， the eigenvectors of M。Are the columns of pe。

The columns of p are eigenvectors of n。Okay you can just check it by actually calculating what happens if I take a PDP inverse and I hit it with a column of P。

 do what do you get， you'll see that it's an eigen vitector。So therefore this。

 once you have this matrix。Its eigenvectors give you the columns of B。

So you can just do this and record the columns of V。啊。And similarly， you can recover。 So basically。

 eigenvectors of。嗯。MG M H inverse。givesives you columns of B。

Which have the V1 through B and like the we are the vectors if you want。 And then if you do M。ex啊。

MG transpose。Times。Emage， transposing verse。嗯。The eigenvectors of that will give you u sorry give you columns of w。

The same it's essentially the same thing with just a transposed， everything transposed。

So then once you get V and W， you can recover you by， you know whatever。

 it can do many things to recover you， it can solve a linear system to recover you。Consol。

A linear system。To recover you。Because I mean， once you have V and W， I mean。

 you have everything sort of quite easy to recover in many ways to recover。

So this is called Enri algorithmga， it's a very simple。I got somebody。The。

It shows that if you have a。In some sense， if your rank is less than n。

 effectively choose that if your rank is less than n。You can actually。Find the decomposing vectors。

 like you can find the decomposition。But we don't yeah I mean。

If this is called an undercomplete tensor， meaning the rank is less than n。

 if your tensor has rank higher than N， then we don't know how to recover。There's no I to recovery。

Okay。And so the key idea is just that if you。Because the tensor is looks like。です。

Tenssor looks like the sum of rank one terms if I you decide on one of the modes。

To start taking random linear combination of that mode， like on one of the three directions。

 you start taking random linear combinations， you take one random linear combination Mg。

 you get a matrix。And if you take another random condition and match， you get another matrix。

 both of them essentially， in a sense， they have the same eigenvaluevectors。

 but they differ only in the eigenvalues。嗯。Roughly speaking。

 they have two mat with the same eigenvectors but different eigenvalues at a very high level。

 and therefore you can just。Like once you hit， you can look at MM mentionedverse and recover the main and so on。

Okay， the question is why did this require r to be less than n the reason it required r to be less than n is I assume that the vectors V1 through VR and W and through wR are linearly independent。

And that was critical here when we did took inverse。When I took M inverse。

 I said V inverse and W inverse。That only makes sense if V and W have linearly independent columns and rows。

And so that's where you need it， this only works for R less than N。All right。

 actually on the I mean I guess I can say on the homework。

 there's a very nice application of Ns algorithm。There are many， many applications of these tensors。

And。Lots of them。嗯。But now I'll show you one application which is sort of easy。你你关兴吃饭。嗯。

Professor I had a quick question， so can R equal n or does R have to be less than that or R can equal n？

Sorry， yeah R can equal n that's sort of the limit yeah。没。Oh yes， thanks。The question was。

 should it give you the rows of w， Yes， it gives you the rows of W。And you use that yeah。Okay。

 so all right， so let me show an application。So here's the application that we will see。

 it's called independent component analysis。Yeah。So， here's the situation。So you have some unknown。嗯。

诶。嗯。SoLet me say the following， you are getting samples。Why？You're getting samples y。

 which is equal to Ax plus B。ok。😊，Getting input samples like this where。X is a vector。

A randomand vector。With independent coordinates。So x is a random vector with independent coordinates。

 well let's say for simplicity， think of it as just random plus minus one values。

Right x is like an n dimensional random vector。Okay。And。He。Its some unknown。嗯。

Inverible linear a transformation。So you don't know the matrix a。

 the invertible linear transmission a。And be some unknown shift。So there are some。

 so what you get is why。Okay。And。Your goal。Is， of course， you want to recover。A and B， and of course。

 once you recover A and B， you can also start recovering this will also imply that you can recover x from the y'。

If you keep getting samples for you can take as many samples as you want of Y and every time you ask for a sample。

 somebody generates a random vector X with plus minus1 coordinates。

 applies a compute X plus B and gives it to you。对。And the only thing you know about x is that it has independent coordinates。

All right， so this is related to this。Question it's called the cocktail party problem in， I guess。

In signal processing is where this came up so the cocktail party problem is imagine you're listening to the conversation in a cocktail party and device listening to conversation in a cocktail party there are all these different voices coming in all of them you can think of them as independent。

The independent of each other。You have samples from some independent distribution。

 but what you hear is not individually the samples， but some mixture。

 so some linear combination applied to them。Okay and your goal is to sort of disambiate the independent components out of it or recover each of the independent components from the signal that you're receiving。

And。This is like a formulation of that。Of course， I'm adding that noise here， you can always add。

 you know， the problem doesn't change much。You can always modify the algorithms that we can see。

To handle some additional Gaussian noise or something or some noise at the end， but for the moment。

 let's say there's no noise。So he's just getting samples from ax plus B。Okay。Is the problem clear？

Okay， so。You。Alright， so let's。Let's see how to do this I mean firstly。Okay。

 I'm getting samples from y equal to ax plus B。getting wise， have y1， Yt and so on。So。嗯。So I mean。

 like one natural thing you would want to do with data is to center it。So what is centering。

 I'll just subtract the mean。Of the data。Okay， by you know。Essentially。

 what I' do is I look at Yi minus the average of Y。As my new data。ok。Remoing the mean， basically。

Shifting the mean to be zero。Okay， the effect this has is we can see that the expectation of why。

Is basically expectation of Ax。Plus， expectation B。Of course。

 expectation of ax is zero because for the moment let's assume that x is actually random plus minus1 for this for the rest of the lecture。

 let's assume that you can also handle more complicated distributions but for the moment let's assume that x is random plus minus1 so expectation ax is0 so you just get B。

It's the expected value of y is B。So if you subtract the expected value of y。

 you can take samples and you shift the mean。Then you don't have to worry about B anymore。

your new samples after centering。嗯。You can assume that you are dealing with a problem where B is equal to zero。

So y is equal to ax。you're dealing with the samples situation where B is0。几。O。ow诶。

Okay so what's the natural thing to try after you do a centering centering is just computing the mean and subtracting right the other thing which people try to do with data is to do whiten it。

Wning whitening is basically。You know， you。诶。You， I mean， essentially whitening is。

Putting the vectors in isotropic position， you compute the covariance matrix。

 you apply a linear transformation so that the covariance matrix of the data becomes an identity matrix。

ok。to you。That's what whitening is， but you know we don't even have to go that far。

 let's just see what happens if I just compute the covariance matrix。Okay。

 let's just compute the covarience matrix and see what we get。Covariance of y。What is that equal to？

Because we centered it， expectation y is zero。The mean is zero now， okay。

 so now what is the covariance matrix？It is this quantity。

It sort of gives you the ellips side right the thing we talk about usually so it's the it's this quantity well it's expectation y y transpose because expectation y is0。

And this is actually。嗯。Expectation。诶。A X， X transpose a。It transpo。ok。

And that is a times expectation xx transpose a transpose。Right that's a。

It move the expectation in because A is fixed。Now expectation xx transpose what is this matrix well expectation xx transpose is the matrix with whose entries are。

Let's just see what it is， it's the whose entries are expectation X I X J。

RightWhere X I Xj are random。Plus minus1 values。That's what we decided x is from So expectation X X J is actually0 if I not equal to J。

And one ne equal to the。So expectation xx transpose is just the identity matrix。Okay， so let's know。

So basically this gives you AA transports。All right， so the covariance matrix of y。

It givess you AA transpose， that's nice， so it's basically giving you the matrix A in a sense。Okay。

 then what's wrong， well it just gives you a transpose， you can't recover a from it。In fact。

 it's impossible to recover a from AA transpose from AA transpose。It's impossible to recover a。

Because。嗯。Because， you know。In some sense。If I apply a rotation in the middle。I get the same。嗯。

A transpose is also equal to A AU transpose for a rotation matrix a。Maric C for rotation matrix。

Rotation matrix is in something which has etransposive identity。Okay， if you take a rotation matrix。

 its sort of and this is a。嗯。This is an issue with low rank decompositions in general right when you take a matrix and write it as a low rank decomposition。

It's not unique because there's a rotation issue whenever you write m equal to U you know A B transpose。

 you can always insert a rotation in the middle and youd still have the same thing。

So up to rotations， you can recover the rank matrix low rank you know decomposition。

 but you can never disambiate the rotations。Okay， and that's the issue with matrices。

That you can never disambiate the rotation there。But it turns out that once you add in higher or degree information。

 once you look at three tensors or four tensors。This rotation issue goes away。

 we can never uniquely recover。The pieces in。Okay， so theres a question which says what the model。

 which is asking what the model is， the model is as follows。

 think of it as every time you ask for a sample of why。each sample of y is generated as follows。

X is sampled from an distribution where each coordinate of x is independent， so x has n coordinates。

 each coordinate is let's say random plus minus1 value and somebody samples x computes a x plus B and hence y equal to a plus B to you。

Just like in the cocktail party， everybodys speaking simultaneously and what you。

 what you hear is some linear combination of them。Of those independent signals。At every time stop。

I have a question like how， how is it possible to distinguish what the columns of AR and like the order of them。

 because like if can， can't you have like a random vector。

 like the permutation of a random vector who else does the same probability as like。

Another like a permutation of it right so like how would you distinguish the columns of a from each other right like even in like just like just like from like a like just just looking at the problem itself like you know like could an a if you permme the columns what do the same thing as permeuting the entries and X and how would if it's if it's a distribution how how would it be like right yeah yeah。

 you're okay so to asking。How would you be able to distinguish yeah。

 you won't be able to only able to recover A up to permutations。Yeah。

 I guess well cover A and B up to permutations。嗯。So I mean。

 in particular regard the signal up to permutations。

 which sort of makes sense I guess you have it's a bit like in this cocktail party prom。

 you can recover the different voices， but there's no particular order on the voices that you can。

And force， we can record some some order of the yeah。You're right， yeah， so you cannot and B。

 you can opt to peration， that's a good point。Yeah。That's right。

And so actually what's happening here is we that right， we are actually， yeah。

 when we look at the degree going back， we look at the degree two moments。

 you're only able to recover it up to a rotation。Which is sort of not what we want and won't disambigate this rotation。

So let's see how to do this。So okay， so the natural thing to try is to try looking at higher order tensors。

Because you're getting samples from Y you can。You know can you can estimate all the higher order tensors。

 so for example。You can estimate。This higher order tensor， Y tensor y。Densor y， tensor y。

Its expectations。 So， so this is a random。For tensor。Right， it's a four dimension array of numbers。

 each of them is random， and then you can estimate its value， estimate its average value。

By just taking a lot of samples， you can estimate the average value。

Its it the degree four moments of the distribution。Okay， and。呃。I guess you know what I'll do。

 I'll just。Throw something at you just another identity。If you define。M4。Is equal to this minus。比。

With啲。Is the fourtensor。Whose ABCD entry is the following。嗯。I it's not difficult to arrive at this。

 but。Let's just。Skip ahead。O。So let's just keep ahead so we have this。This ten a T。

 note that the entries of T are given by pairwise correlations between the coordinates of y。

The ABC entry is this term it's a product of three pairwise correlation。

 you know it's some of these three products of pairwise correlations and you can estimate this number。

 estimate this tensor。Right this you can estimate。Just by sampling and estimating all the pairwise correlations。

All these expectations you can estimate by a lot of samples and then you get an estimate for T。

and if you have a lot of samples， you can estimate M4， which is this difference。Okay。Alright。

 so what is nice about M4， Well， actually， M4， if you expand it out， it looks like this very nice。

Thinking。It turns out to be。The four tensor。Of the columns of the matrix a。Times Ka I。

 where what is Ka I， Ka I， these are the columns of a。And Ka I is。细衰。Just。だけかい。ok。So that looks nice。

rick so now。Let's assume that this Ka I numbers， I mean， we assume that effects is plus minus1。

If you assume x plus minus1， this is just expectation X to the4 is11 minus3 is minus2 right so we don't have to。

We know what the cap is are， but if is any other distribution also it's some number。

 it's some fixed number。Okay and let's assume that the copper is are not zero。So if ks are not zero。

Then you are in a good position now。Well， what， what's the situation now， you have a。

You have a four tensor。Who's a。Which is like a rank n fortensor。It's a rank and fortensil。

So you can basically run。An algorithm just like Enris algorithm to recover AI。

So there are much faster algorithms to do it like or much better things to do than to run Ens algorithm。

 but you know， since we covered Ens algorithm， let's do it， I mean。

 the faster algorithm would be to not you know just do some sort of power method type computation to or even。

As we said gradient accentcent， right this gradient accent to record one of the AIs， but you know。

But you can just directly apply N algorithm to recover the As。And once you record， the eyes。

 you are basically done。Okay， and。That's the sort of the。嗯。Id here and okay。

 so one thing I said was the cap I should be not zero。

 so I don't want the fourth moment for my randomberry black eye to be three。

So this algorithm fails if expectation excite to the four is three。Okay， if this happens。

 the algorithm fails。And it fails for a very good reason。The reason it fails。Is because。

Imagine your excise web Gaussian。Like I conveniently said my x is are random plus minus1。

 but if my x is were Gaussian， the Gaussian distribution is independent is。嗯。

Is symmetric kind rotations， it's rotationally invariant if I take the Gaussian distribution。

If I take a random Gaussian vector and rotate it， I get a random Gasian vector。Okay。

It's verylyly symmetric。Every rotation is also there what that means is if x ispherly symmetrically distributed。

 there is no way you will disambiate。The rotations its impossible to disamiggate the rotations if x is Gasian。

So that's what it's happening here。X is Gaussian。It is impossible。To recover it。

Just because of this rotation problem we talked about。

If every rotation looks the same then it is nothing you can do， you can't disambiate the rotation。

And。If X is Gaussian is what happens V is Gaussian， it's impossible to recover and in fact。

If the fourth moment of a Gaussian random variable will be equal to three。Is equal to three。

And this is precisely when it fails。In fact， it's a。Quite a surprising fact to me， at least that。

This is a characterization of Gaussianness。嗯。That if I give you a random variable。

 whose second whose。mini zero。Its first second moment， its variance is one。And its fourth moment is。

3。I think these three facts together imply a taxise Gaussian。

Somebody can correct me them if I'm not getting this right， but I think this is true so。

So really like this just this' unique distribution where the fourth moment is three。

And that's going to be the Gaussian distribution， which is a rotationally symmetric。

 and you can recover Xxi。Yeah。Any questions？So are Gausians the only spherically symmetric distributions？

great question， actually， Gaussians are not the only spherly symmetric distributions。

 but Gausians are the。嗯。Only distributions。嗯。That。It'spherly symmetric。嗯。And preserve the。Like，嗯。

And get the。Per the L2 what do I mean I mean。They're the only something called a two stable distribution。

So it's the only spikely symmetric distribution。In fact， it's the only distribution。Well I'm sorry。

 it is the only veryly se distribution whose linear combinations are also the same。I mean。

 it's easy to constructpherlysymmetric distribution students you can take。

Any distribution and sort of rotate it and take average right that gives you a casesphericlylisymmetric distribution but Gaussians are more than justpherlyisymmetric in that any linear transformation of the vector。

Is also a Gaussian。Read。It's a too stable distribution in that sense。

And that's the only way in which。You can be completely fooled。I guess another way to say it is。

If it was a case that by taking linear combinations， you change the length of the vector。

In some reasonable way， right， like if the length is not something that's。Take个。

Right like if I take a linear combination。If I get if I don't preserve the distribution like if a has a different distribution than x when I take linear combinations then you can still distinguish I think so Gaussian is the only case where and every。

Linear transformation gives you like a gausian with some with the same scaling or with the appropriate scaling。

错那。や only。Okay this's a question about how do you apply Nx algorithm to to the four tensor here I guess there are many ways one thing is you can just make it into a threetensor by losing some information you can just compress one mode for example sorry we were here right yeah you can just compress one mode like you can like for example just throw away one of the modes right meaning look at the first slice if I give a three tensor we look at the first slice I get a two tensor similarly if I give a four tensor you look at the first slice like in one of the directions。

One of the four directions that gives you a three tensor and that's good enough。 but if like I guess。

Yeah， I mean， if you would like the correct way to do it would be to compress one of the modes by hitting it with a Gaussian or something like a random。

 take a random linear combinations along one of the modes， you get a three tensor。

And then you can apply NR algorithm。嗯。But you know， there are other things you can do with1th。嗯。

Right so what is a tensor eventually it's like a three tensor is just a three dimensional array of numbers in some sense right so if I give you a four tensor you can also do the following you can treat it as a three dimensional array of numbers where。

The first one is the like one of the dimensions， the other one is the other dimension and the last two together。

Is a third dimension so the first dimension ranges from one through n。

 the second dimension ranges from one through n， the third dimension ranges or n squared different values。

 it's a bit you know it's not same length all three direction， but then that's also fine there。Yeah。

Okay， there's another question， could we just throw away two dimensions and get an eig decomposition no then you have end up with a rotation problem again。

啊。LikeOnce you， get to a matrix， you have the issue of rotations。啊。Scision throw it。Yeah。

What you should do is actually， maybe you can。Just throw away one of the derivative dimensions by taking a random combination I get a three tensor and as an N algorithm should construct two different matrices from three tensor。

And then you'll meet。Pretty you can do if you can flatten out a tensor in any way you want。

 that's actually a useful trick sometimes if have a four tensor， I can write it in as a three tensor。

In like multiple ways。I can write as a matrix also， right， for example。

 I can also write the whole fourtensor as a matrix by just treating。

This whole thing has one dimension and this whole thing has another dimension。

 so it's an n squared by n squared matrix and n to the four like a four dimension that is also an n squared by n squared matrix and you know all kinds of things like that。

These are called flattenings of the tensor。Can flatten it in many ways。Good opinions。

So next time we'll actually talk about。The next section uses like dimension reduction embedding and on。

Thank you。

![](img/be20867f8bd456f48459895c984dd9b5_5.png)

Iside hey good Oh， sorry， you're still recording。

![](img/be20867f8bd456f48459895c984dd9b5_7.png)

嗯。