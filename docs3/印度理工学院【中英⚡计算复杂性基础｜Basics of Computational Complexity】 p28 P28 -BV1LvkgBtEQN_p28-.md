# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p28 P28 -BV1LvkgBtEQN_p28-

![](img/203fec5ba8b522eb70718ca770626d16_0.png)

So， now， we will see。A more non trivial， Shaie， complete problem。

 which will be interesting because of。It's algebraic nature。Okay， so。

This will be a very basic problem inspired from determinant。Or inspired for matrices。So， for。

Matrix E。For an encrosscent matrix。Go some feel left。Let's call the matrix a。Permanent is defined as。

So permanent is the following value。It's tough。Some of product of。um。Elements in the matrix。

 but very special elements。These elements will actually correspond to。Picking in。Locations。

None of which share a rule or a column。O， so they will correspond to what are called permutations。So。

 I and N。E I sigma。😔，Overall， the permutations。In case of sigma， this same n is the symmetry group。

The group of symmetry on elements 1 to n。 so they n factorial size。And。Basically from so I。

 if you think of i as indexing the rows of the matrix a。

Then it is just picking distinct columns and mapping it to the rows。Okay。

 so there are n factorial terms。In the definition of permanent。So， Sim is。The group of。

N factorial permutations。Of in。No。😔，Notice its similarity with。Determinant。So what is determinant。

 determinant is of the same matrix。Same expression。With a tiny difference。

Swim expression except the difference is that here we will put a sign after before the product。

So that's the sign of the permutation。Okay， so this sign。

 basically the the symmetry group has half odd permutations and the remaining half even permutations。

So they are divided to plus 1 and -1。And that's the sign you have to put here。

 You don't need to know the definition of odd and even permutations。

 but just remember that half of them will have negative sign。And that changes everything。Okay。

 so this is determinant。 and earlier thing is permanent。 As an exercise， you show that。Determinant。

Is an F P。Okay give a deterministic poly time algorithm for determinant。

 although the definition has n factorial terms。Yet， it is in FP。

So though it has n factorial terms with plus minus s x still。You will be able to give an algorithm K。

 using the symmetry。Of the group。 And this is used everywhere， of course。

 in linear algebra and engineering。嗯。But what about permanent now So coming back to permanent。

Nothing like this is known。Okay， the only algorithm known is essentially this definition。So。

 that's exponential time。Su。We'll see that。Permanent。Is。The hardest problem is Shaie。Okay， so in。

So first we will show that permanent isn't sharppy。And next， we will show。

 which will be a longer proof。 We'll finish it next time。That actually。

 the hardest problem will Sha be complete。 So it is at the level of shop set。 Okay。

 just like shop set。We don't expect to find a fast algorithm， similarly permanent。

 We don't expect to find a fast algorithm yet at the same time。

 determinant somehow has a very fast algorithm。Okay， so， so that's this。

 that's a surprising mathematical fact。And conjecture。

Let let me not say the just permanent is a hard test。Is one of the hardest。ok。

So first is what is it to do， what is permanent to do with the Shaie。So permanent for 0，1 matrices。

Is't shopping。That's the first thing。Why is that。What is Sha set。

 Shapy to do with permanent that is not immediately clear， but then。You think about it。

In terms of guessing。And in design and N team。😊，Which cases sigma。Okay， the set of sigma。

 the symmetry group is huge。But once it makes a guess on sigma。

 then it can actually identify those entries multiply。The entries to get 0 or 1。

Okay let's design that entity。So let E B。0，1 matrix。En crossen。Permanent of is。The number of。

Pomutations。Permanent is number of permutations， such that。

This product of those entries and entries is one。So if you look at it in this way， then you see that。

呃。This can be solved by an entityium， polytime entityium。

With the number of accepting parts is the number of these sigmas。So， permanent。Equals the number of。

Accepting parts。Of the indie team。That given E。Gsses sigma。So number of these correct sigmas。

 which will be。The number of ones others are zeros product will be0。 That is why we needed0 or 1。

Entry。So， that's。Hence， we conclude that permanent reason。Permanent 0，1。Is in。Sopby。😔。

And this 01 permanent， there are many results， but there is no fast algorithm known。So permanent 0。

1 has applications in。Computal physics。And probability。

There are also approximational algorithms known。If will not do that。

 but you can do it as an advanced topic if you want approximational algorithms for the real permanent。

01 entries。It has interesting connections through。Mixing of Markov chains， and such。

So what we'll do here， though， is。That it cannot be exactly computed。呃。

Or it is not expected to be compable in polynomial time because it's sharpie complete。Okay。

 that is what well show。And for that， we need a graph interpretation of permanent。So， let's do that。

So given a matrix and to n。View it as。Vi it as the adency matrix。O。Weed di。So direct graph， right？听歌。

The matrix as an agency matrix of a weighted directed graph on n vertices。Where are the weights。

 the weights are on the edges。Okay， and the diagonal entries， you can think of them as loops。

 weighted loops on the vertices。Edge weight， think of it as an edgeated。Diagraph。And then。

So let me maybe draw it。And there might be loops on these vertices。And on the edges， there are。

Weights， so that can be anything field element。Can be-1。 It can be 0。 It can be-2， can be one。

It can be4。 It can be。-10。Okay， so。These are the vertices，1。Du。😔，3。Okay， these。

 these are the vertices and then you have the edges， which are all。Waied。

So this can be represented by 3 by 3。Matrix。And there might there could also be these edges。

 It's a directed graph。 So you， anything is possible。Okay。

 so overall you can count that this there are  nine integers， nine field elements。Re as a matrix。

 So next concept that we want to define is to do with cycles。

 but maybe the cycle doesn't cover the whole graph it covers a part。

And then look at a disjoint cycle and so on。 So look at a cycle cover。So， cycle cover。See of this。

Weed diagram E。Is a sub graph。Having invertices。Each having。In degree out degree 1。Okay。

 that's the main thing that。It just， just think of a sub graph， which is。A union of disjoint cycles。

So for example， it here it can be。嗯。Vn。There's the vertex 1，2，3。And the sub graph we are considering。

Of in degree of degree 1。Is let's take the zero loop。And then， take。This loop。Okay。

 the0 loop on one and the 1 minus-1 loop on。2，2，3， and back。So this is this is a cycle cover。

And there are many sub cycle covers， you can see。Okay， there are two more sub cycle covers。So。C。

Is a union of disjoined cycles。Right like in this picture， union of two designjoin cycles。

 that is a cycle cover。And we define the weight of a cycle cover。So， weight of a cycle。Is defined as。

So if we of a cycle cover this sub graph， right， this is defined as。嗯。Product。

Of the weight of the edges。In the cycle cover。OkaySo in particular， in this example。

 it is 0 times 1 times minus-1， which is just 0。So that we call the weight of the cycle cover。

And why did we do all this？We did this to giver。To interpret permanent。

Using graph it it is actually permanent of the graph or matrix a is a property of the graph that a。

Specifies。And。It happens to be some of overall cycle covers。Permanent of E is the same as。

Wet over the cycle covers。Xi。So do this as an exercise。Okay。

 this has to do with the well let me sketch it。The idea is， basically。

Cycle the composition of permutation sigma。S say monoommal。Yiwenwen。😔，E，2，3。E，3，2， M， A，4，4。Appears。

Non trivially， impermanent。The permit definition is via sum in the sum suppose there is a term product。

Term corresponding to this permutation， which sends one to one。1 to itself，4 to itself。

 but2 and3 it swaps。Okay， that's sigma perutation。So what is this to we actually want to map it to。

A cycle cover。 That's the idea。So how is that done？So， in the diagram E。Consider the cycle cover。

Suvan。2，3， and 4。 These are the four vertices in the di。

And the edges that you should look at is this loop。With the weight。Ywenwen。2， to，3。With weight，8，23。

And 3，22 with weight， a 3，2。And then again， a loop on 4。

So this has the weight same as this monoommial weaver。Talking about。So， this has wheat。

Equal to that M。 Okay， so this cycle cover。Contribute this much weight。Dhude。Right hand side， right。

Of this equation that we were considering。And it matches with the。Definition of permanent of。

And conversely。So， every monoommial imperman on the left hand side has a cycle cover in the right right hand side contribution and every cycle cover corresponds to a conversely weight。

Of a cycle cover。Ofい。Corresponds to。Corresponds to。Amonumial of permanity。Okay， this is given by。

Cycle decomposition， also。Okay， so this is really a connection between the cycle de compositionposition of permutation。

 So its permit is defined by by。By permutations， every permutation gives you a cycle cover。

 every cycle cover gives you a permutation。So that is what we have written here。Just check that。

And that proves the equality。That permanent。Is the same as sigma over。Weight of cycle covers。

Let's see an example of this。Observation， it's an important observation， so。

Let's consider the matrix， E。0，1，1。-1。0，1。-1，-10。And in the graph form， it is。Vertex 1。😔，3。

The edges are。So。Basically， watch the edge from 1 to 2。 What the weight of that right， so that is1。

And then 2，2，1 is -1。What's the weight from 2 to3？So that's the 2，3 entry of the matrix。That's one。

 I'm sorry， oppositepo direction。3，2 is。-1。1，3 is1。And3，1 is。-1。That's the graph。Of this matrix。

 weed digraph。And let's now list the cycle covers。So how many cycle covers are there。Basically。

Since you don't see any self loops。You have to use these。You have to use three edges， right。

 So once you can go clockwise or anticlockwise。 So there are two cycle covers。 So first is。This。

And another。So let's write the clockwise one or anti clockwise one。 So this is。So22 1 is -1，1，2。

3 is1。3 to 2 is  -1。1，2，2 is 1，2，2，3。And 3，2，1。this is clear and so the weight of this cycle cover is。

This weight is1。

![](img/203fec5ba8b522eb70718ca770626d16_2.png)