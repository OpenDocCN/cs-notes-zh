# 印度理工学院【中英⚡计算复杂性基础｜Basics of Computational Complexity】 p29 P29 -BV1LvkgBtEQN_p29-

![](img/97b7d0ea8d2362c1f3155678580e48d9_0.png)

So， yesterday， we。Averruptly stopped。While we were doing this example。Trying to interpret permanent。

As a graph so permanent is defined via some of monoials。

And each monoommial we want to see as a cycle cover。Now。

 the monoommial corresponds to a permutation of 12 n。Which are the vertices。 So permutation。

 you can see it as a。As recomposing into cycles。 And that is what you。Can visualize as a。

Cye cover in your graph。In the graph， which is defined by E as any decency matrix。

So the example is that we were doing。Vtic is 1，2，3， and there are these。Yit。😔，Weighted edges。

 there are no cell flus。So it actually gives you three。Cs。And hence， three cycle covers。Sorry， not 3。

2。So， there is this。Clockwise。1，3，2，1， and the anti looy is 1，2，3，1。First has wait。

 One second has weight。-1。So which means that。The permanent of this matrix comes out to be 1-1。

Which is 0。Okay， and this you can check that。By definition， also it's 0。

And the same thing you can see in terms of cycle covers and some of weights of cycle covers。

So once you have seen this， now comes the。Comes the use of this interpretation。 the use will be。

Quite stunning。 So we actually use this graph too。S that permanent is the hardest problem in count class。

 Shapy。 So our theorem is。That permanent for 0，1。Merices。Is shay heard。So， essentially。

 we have to show。The shop。3 set reduces2。Permanent shop  three set can be reformted as a permanent question。

We relate shop 3 set。To permanent。So， let phi。Bi。😔，A3 C in a formula。With M clauses。N variables。

And we can assume that without that each clause has exactly three litals。

Like a clause may have two literals or one lateral， but then we can repeat it。

So without possiblegene， each clause has three litals。 So there are these。

M clauses each has three literal， so 3 m。Occurres of literals。Variables are an X1 to x。So。

 the idea is。Construct the graph E。Construct a graph via an edency matrix E such that。The sum。

Of its weighted cycle covers。Equals permanent。I mean。

 which is also permanent by the previous interpretation。Is。The number of satisfying assignments。Oei。

😔，Okay， so we want。To relate sharp  three sets。 So basically you want to count the number of satisfying assignments that will。

Make equal to permanent。 will construct such a matrix。

Constructing this matrix with 01 is pretty difficult， if not impossible。To imagine。 So we actually。

Get this done by。Drawing graphs。And those graphs will look complicated。 will introduce gadgets。

Gra gadgets。To express litals， to express variables， literals and clauses。

 So let's see the implementation of this idea。So， each variable。Xi。Is converted to。A graph gadget。

 V I。So the graph gadget will this we are doing it for doing for variables， right。

 So this variable gadget will have to be connected to。The gadget for the clauses。

 And there are m clauses。 So we actually have。M parts in this vertex gadget。So， let me draw that。So。

 these cell loops。And connected via。Images。These are m plus1 vertices。Here。

 and so there are m plus one self loops here。And two more vertices。To capture。

Truth and falsehood of the variable。 Truth or falsehood， right。So that's the full gadget。

What are the weights？So weight of all these edges is one。Every way it is one。This is the。

This is the true。And this is the false。K the edge below1 is， is the truth。

If it is used in a cycle cover， then it means that the variable is set to true。

If the top edge is used， then the variable is set to false， that is the meaning。

That's the interpretation of this。 And these ones。These are the M external edges。We call them。

So what is happening is if you use the external edges， then you will have to use the true edge。

If you use， if you do not use them。Then you are using the cell loops， and you will be。

Fored to use the falseage。 Okay， so in this way， you can set。the variable true or false。

That is the interpretation how it fits in the big picture that we will see later。

So let me write what I just said。The interpretation is。The cycle cover。Using external leds。Of Vie。

Signifies。Exciite said to true。Okay， while the other。While others signify。That X is set to false。

Okay， so if the external edges are used， then true edge will be used we interpret it as setting X to true true or1。

Otherwise， we are using the cell loops and the false edge interpreted as。X equal to falls or 0。Now。

 each clause。Let's say， Fg， the G close。Is converted to。A craft gadget， C I。So the C G。Which is。嗯。

Yeah， this will actually look simpler than the verortex gadget。So here， what we will do is。

Remember the clauses， each clause has three literals， so we will kind of add here。three cycles。

 depending on which lital has become true。So it will be like this。And in the internal connections。

So these are the external edges。These are three external edges， instead of。And plus one。

 because now we are looking focusing on the clause。And the clause gadget has interpretation。

 It is related to three litals。So there are three external edges。And the internal connection is。

As follows。It so。As always。Unmarkgged weights are one。 Just assume that。It's unmarked edges。

Have weight equal to。W on。So what is the interpretation of this。So， here。

There are three cycle covers。Could you see these three。Basically， you can use one external edgege。

Then two internal edges。And another external edge that will give you。A particular。Cycle。

 and you can do this in three ways。 So there are three cycle covers。Each of weight，1。

Each corresponding to。To a dropped external edge。And。The latter， the one which is drop， that means。

Interpretation is that that variable is or literary set to true。So， the latter signifies。Phrase。

Third。The corresponding lital。En FT is true。Okay， the one which is dropped。 So here。So for example。

 one example cycle cover is。You can。Big this。And then you can pick this。 Then you can pick this。

 and you can pick this。Okay， so in this case the drop one becomes。This。Right。

 so here is a cycle cover these yellow edges， which I have marked。This gives you a。

Cycle because it is cycle cover because it is covering all the four vertices here。

And it leaves one external led， which will。Which we are thinking of as literal said to true。其 so。

Always a cycle cover here in the clause gadget means that。Signifies that the clause is true。

 because some。Literally true。But these two things currently are independent， right。

 we drew we drew a variable gadget and we drew a clause gadget。

But this information has to be connected。So we also need a connecting gadget。Su。If X I in FG。Then。😔。

The Geth external knowledge。Of V I， the vertex gadget V I。Is connected。Do。Do。

The X I external knowledge。V V prime。Of the clothes。Of close gadget CG。Buy a new gadget。

 which we are calling。Zor。Connecting I2 G。Suberts I。I use vertex gadget to。Jith， close gadget。

 you have to make a connection。The two externals have to be matched。Su。That is done by Zor。

 So this is the most complicated gadget， because itll connect。These two much simpler gadgets。

Connection means what will connection force。 The connection will force that this。

Interpretation that if。X I is set to true， and X I appears in FG。The F should be true。Okay。

 so any cycle cover should actually。Pass through the right external edge of X I of V I。

And the right externally should be dropped。In Cji。So that will be done as follows。

So let me draw it first。Then you try to understand what is happening。There are these four vertices。

 forming a cross。So， you。Is connected to this， and。You prime is an outage。The opposite here。

Then I get give cell flus to these。Hences。And。I gave a loop here。I give a connection here。

And I give a cycle。And I also give opposite edges。Only years。Now， interestingly， here。

 we will also need some negative weights other than， I mean。Unmarked ones are one。

 but well also need。-1 end。2 in three。Becauseuse well want the cycle cover contribution of this connecting gadget to be 0。

Thatexhui。I need one more edge。Give it3。So， again， the interpretation is。

Or let me first also make this。Definition complete。 So if X I is literallyal in FG， then。

Will connect the。G8 external ledge of VI， which I think we are calling it U U prime。

So the Gf external edge in the verortex gadget。Okay， if that is U U prime， then this。

 this is how the connections are done。 So you U prime。Is shown in your resort gadget。

And then v V prime， which is the。One of the three external ledges。Of the clause gadget。

That's also shown in this zorar gadget。Okay， so this will allow you to basically pass from the。

From VIe。Through the zar gadget，2。CG， that's the idea。And maybe X bar is a literal。

 so then we will do something else。So， if。Xxi bar is a literal。Then。The false edge， because X I。

 you are forcing it to be you want to force it to be false， right， So you have to。Now， work with the。

Not the external age， but the fault。Edge。😔，Then， the false edge。Yy prime。Of V。😔，Is connected。Do。

Exi external knowledge。Like before。We are calling it V V prime。Of Cji。This is done by。Z right 이제。

OkaySo this completes the definition。 you use。This zg gadget to connect the correct。Edge。

Of V I to the correct edge。In Cg and the yeah， let me give the interpretation。So， here。

The interpretation is。Appropriate。Truth or false value。Of exc。Forces。嗯。The correct。Cycle cover。

To be picked。yin。Xizhi。😔，It which corresponds to F she。And X corresponds to VI。

So the path that you are taking inside V I that actually forces。

That corresponds to truth or falsehood of Xi。 and then it gets transferred via the zar gadget。Do。

The clause gadget， C G。Okay， that's the idea。 this U U prime gets transferred to V V prime in the language of cycle cover。

 So the final graph looks like the big picture。After all， these small gadgets are connected。

The big picture is。So， the graph E prime。In the big picture。Is。You have the。Vertex gadgets。

You have the claws。Gdgets。And V I and Cj connected via Zor gadgets。But remember that C G has three。

Liter right， So X is just one of them。 X or X bar。 So other two are also present like this。Bensonn。

So that's the， that's the interpretation。 So this， these are the vertices。

These are the close gadgets。And in this layer， you have the zor。Gdgets， Okay。

 so these are the gadgets。So as you can imagine， N vertex gadgets， M close gadgets。And 3M。

Zor gadgets。So let's fix our understanding。In this claim， till now， what we have done is。

There are n vertex gadgets。M close gadgets。And。3M source。That's obvious from this picture。

 from the big picture。U。Second claim is that the cycle covers of zar。Some28，0。Okay。

 so remember that if you want。To compute the permanent of this graph。That' is a complicated formula。

 so we will break down the calculation into smaller parts。So first we'll analyze。

 first we analyze it gadget by gadget。 So I， we will look at。

The contribution coming from Zor and that we have made sure is 0。That is what I will prove。

And the other contributions from the vertex clause gadgets you can see is one。

 so it will help us in doing the counting in this graph。So。

Or remember that these edges which are unmarked， they also rate one。Right。The the other than one。

 we have -1，2 and 3。 So there are only。4 possible values。And obviously， it's  zero。

 If there is no edge， then it's  zero。 So it's。Either 0，1，2，3 or  minus-1。

 those are the values of edge weights。And， let's now see。What is the contribution of Zar gadget。

Minus U U prime V V prime。So， cycle covers。Inzor。Gdget minus。You，y prime and V V primeme。

Because U U prime V prime are actually in the in other gadgets right these are vertic in other gadget gadgets。

 the vertices of zor， how much are they contributing lets do that So you can either use the cell loops of zor or not。

And。Then， they are these。Forwardwardage， backwardage。 you can use that or not。So accordingly。

 you will actually get four cycle covers。 let me write that down。You can verify later。

 So the first cycle cover is it looks like this。So I am drawing it so that it's easy for you to verify。

 This is the。Top left。Forwardward， backward， and。Bottom right。Forward backward with width，2，3。

There are only four vertices， right， So this covers all four。Of Z。Next is， yeah， So next is now。

The full cycle。Which goes like this。So do。The exceptional weights are -12， and the rest is 1。

And two more。 so well do this soon。

![](img/97b7d0ea8d2362c1f3155678580e48d9_2.png)