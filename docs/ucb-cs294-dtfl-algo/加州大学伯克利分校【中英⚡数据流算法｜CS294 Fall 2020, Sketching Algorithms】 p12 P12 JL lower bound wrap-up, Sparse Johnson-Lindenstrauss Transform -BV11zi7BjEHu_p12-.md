# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p12 P12 JL lower bound wrap-up, Sparse Johnson-Lindenstrauss Transform -BV11zi7BjEHu_p12-

![](img/516e90b646ce0b30b79b92b896ebe8fd_0.png)

Okay， so today I want to wrap up the proof of the optimal lower bound for Johnson and Mtra。

 I apologize that the lecture notes didn't go up right away， but I did put them up yesterday。

And then once we wrap that up， I'm going to talk about how to speed up the actual time to do the embedding in a jail embedding。

So let's first wrap up the jail lower bound proof。And you know， I just want to walk over this。

 this is stuff that we talked about last time， the key takeaways that we can continue。

So remember that the whole way the proof is organized is we don't just have one point set。

 but we have a collection of point sets。And we're going to show that if it's true that every point set in the collection。

Has a low distortion embedding into low dimensions。

Then we have an injection from that collection of point sets into a smaller set。

 which is a contradiction。Okay。And what is this collection of point sets。

 it's actually ordered point sequences。And if the endpoints are zero。

 together with the D standard basis vectors， EI means you have a one in the I position in zeros elsewhere。

 together with YS1， Ys2， et cea， up to YsN minus d minus1， so you have exactly n vectors。

And Ys is the indicator vector for the set S。Okay， appropriately scaled to have unit norm。So S。

 as I say here。S has size K。 that's right here。So says size k and K is this one over 100 epsilon squared。

And the indicator vector of S means you put a1 in the if position， if I is in s， you put a zero。

 if it's not an s， and then you scale it by one over root k。So that it has unit L2 norm。

 so1 over root k is 10 epsilon by my choice of k， so entries in Ys or either 10 epsilon or0。

 depending on whether or not I is and S。How many possible point sequences are there while the first D plus 1 are fixed。

 the next n minus d minus1 could be arbitrary。There are D choose K choices for any given S。

 raise that to the n minus d minus one power because that's how many ss you're choosing。

And then the logarithm of that is， you know， just roughly N log n， okay。

 if you assume that D is enter log reppson， which we can speaking that's I'll show you how to remove that assumption later。

Okay， other things I want you to remember from last lecture。

 we talked about entropy numbers or covering numbers， so basically we have a set。

And you want to have take an epsilon net of that set under some norm。Okay。How small the net？

Can you come up with and achieves this So we had one argument via packing and a volumetric argument to via packing that showed that if you take the unit ball of any norm。

ok。And try to find an epsilon net of that unit ball under the same norm。

Then the number of net points you need is at most roughly one over epsilon to the D。

001 over epsilon to the D where D is the dimension。Okay， good。Okay， so now。The name of the game is。

We're assuming that every point set capital X in script X。

 every single point set has some low distortion embedding， and as we saw last time。

 low distortion embedding means you preserve dot products up to an alu epsilon。

So for a given point set x or point sequence x， point sequence x， there is this embedding F。

 I should really call it f sub x because it depends on x。ok。

Such that all the dot products within capital X are preserved up to an add of Epsilon after you apply F。

And if F embeds into dimension M。I want to show that the fact that such an F exists。

For every point set in this collection means that there exists an injection。

From this collection of point sets into bit strings of length and M。Which implies， of course。Right。

 this implies use this implies that。And M is omega loggged with size of x。Right， which is omega。

And K log n。And then you cancel the ends。And you get exactly what you want M is omega k log n and right what if k K is roughly when e rhpsson squared？

So yeah what else on squared log in and lower down。So now the question is， what is this injection？

Okay。So take one， which we actually talked about last time is。

You look at F applied to all of these points， F of0， F of E1， F of ED， F of YS1 f of Y2。

Now these are M dimensional vectors each。And the entries are real numbers that have infinite precision。

But you know that。All of these vectors originally had unit norm， means zero has zero norm。

 but the rest have unit norm。After you apply F， their norm is at most roughly1。

 it's at most roughly one， you know， it's at most one plus epsilon。Right。

 so these are still roughly unit norm vectors， which means that no entry in the vector can be bigger than one in magnitude basically right or bigger than one pluspson in magnitude so all the entries。

In each vector， after you apply F are roughly between minus1 and1。😡。

So what we're going to do is we're going to discretize the interval。😡，From minus1 to one。

IntoInteger multiples of gamma， so think of gamma as some very tiny thing like 0。01。😡，Right， so。

I'm just going to say， look， there are these discrete points there， there's 0， there's 001。02 。03。

04 all the way to 1。00。And whatever my entries are。

 I'm just going to round them to the nearest multiple of 0。01。

 and I'm going to round them to the nearest integer multiple of gamma， so gamma is 001 here okay。😡。

So now after I do that。I claim that there's still enough information。based on these rounded versions。

 there's still enough information to figure out what the point set was or what yeah。

 what the sequence of points was。Why， because before you did the rounding。

If you just look at all the EI is dotted with the YSJs。

Knowing all those dot products told you what all the YSs were， what all the ss were。

 because if a dot product is 10 epsilon， I is in S， if it's zero， it's not an S。😡，After you apply F。

It's either going to be between nine and 11 epsilon or it's going to be between minus epsilon and epsilon。

 but still there's a gap， it's either going to be at least nine epsilon or at most epsilon or at most two epsilon。

 sorry。😡，At most epsilon， so there's still a gap。And then even the claim is that even after you round the entries to add it to integer multiples of gamma。

 there's still a gap and why is that so let's take let's look right here。😡。

I'm taking these vectors and I'm imagining that I'm rounding the entries to the closest multiple of gamma。

 and then I'm taking the dot product。What does that new dot product look like？

Well it's the sum over I from1 to M of that entry plus or minus the error introduced by rounding times f of y I plus or minus the error introduced by rounding。

 then you just use the distributed law。This is equal to the actual dot product I cared about。

 plus minus some error terms。So I have terms that look like gamma times in magnitude at most the absolute value of F of Xi。

Summed over I， so that's basically the L1 norm of F of x。 so I have an error that's at most。😡。

Gmma times the L number F of x。 I also have an error that's at most gamma times the L number F of y。

 and then I also have gamma squared。RightFrom those other terms。

 the plus minus gamma times plus minus gamma I have a gamma squared term， and I have that M times。

 so I have another error that's at most m times gamma squared。

And now what I'll do is I'll use khi Schwartz， right， kshi Schwartz says the L1 norm is at most。

Squared of dimension times the L2 norm。So this thing is at most。Root the dimension times the L2 norm。

Same thing here， this is at most root dimension times the L2 norm of x， f of x。Yeah。Okay。

 and we know that the L2 norm is basically at most one or one plus epsilon， right。

 So this is now the actual dot product I care about。Plus or minus， you know， roughly1。

 so plus or minus o of rootM。Times gamma。Plus， m times Gahana squared。Yeah。So if I choose。

 I can choose gamma， I'm choosing what precision I'm rounding to。

So I'll just choose gamma to be something like you know， epsilon of a Rum。Some a small constant。

Time's epsilon never。And then this will be the actual dot product they care about。

Plus or minus an error term of epsilon。So before the dot products were either less than epsilon or bigger than nine epsilon。

 now they're less than two epsilon。😡，Or bigger than8 eps long， there's still a gap。😡，And， you know。

 now how many bits does it take to write down a number， well。

 there are only o of one over gamma numbers， you know。

 only one over one two almost o of one over gamma multiples of gamma between minus one and what？😡。

So that's log， whatever gamma bits。So log whenever gamma bits per number。

M numbers per vector and vectors， that's basically the total bit complexity of writing down all the vectors F round。

 and you know that that has to be mega。And K log n。

 that was what that's right what we said over here， right？Basically here。

 it has to be omega and K log n。The ends cancel。You can move the log over here to the。

To the denominator。You knowNow gamma itself depends on M。

 so you're saying that M is omega something that depends on M， but you can solve that asymptotically。

 this implies that M is omega。One over Epsilon squared log and over log log and plus log over Epsilon。

So you do get something that's like almost right it's just not quite right。

 so how do you fix that so now let's do the new stuff。Any questions about that？

Let give you guys like。5 seconds， in case anyone has a question about this。And this is。

Everything I'm saying about the lower bounds today。

 including the stuff we didn't get to on last Wednesday is in the lecture notes。

 so if you want to go through the calculations more carefully， it's all there。

So let's do take two so take two we want to we want we want to basically eventually want to we hope now we can get rid of this denominator here because that denominator should not be there Okay。

 so how are we going to do it。Take two is， look， we rounded to make sure that entry wise were always within gamma。

Essentially， that means that we took an L infinity net。

Of the sphereear so you know we took the we took the L2 ball， the Euclidean ball。

 we took an L infinity net of the L2 ball， and then we rounded points within this L infinity net。

 meaning that every entry was preserved up to this gamma。So now it's instead round to an L2 net。

Suppose that。You know， I round to that f of x， tilde minus f of x。

Al2 norm is that most epsilon here F of x。Is like closest point。In an L2 net。ok。Then what do I have？

I have that if you look at。嗯。F of x tilde dot with F of Y tilde。

Because we're going to write down as our know for our injection。

 we're going to write down the rounded versions， so the question is from the rounded versions。

 do I have enough information to be able to distinguish the eight epsilon from the two epsilon right？

Am I only changing the dot product by another epsilon？Okay。So I can write this as。

I'll just basically add add add and subtract the same numbers that I basically get know0。

 This is equal to。F of x。Plus。F tilde of x minus f of x。So I just added and subtracted F of x。

 so this is still F of x dotted with。F of y plus F Tilda。Why why is why。

And then I can again use distribution and say， look， this is equal to what I want。

 it's equal to F of x dot with F of Y。Plus。And these are the terms that are error terms。Plus。

 I have something like F of X。Dotted with。F tilde of y minus f of y。Plus。

F of y dotted with f tilde of x minus f of x。Plus。F tilde of x minus f of x。

Dotta with F tilde y minus F of y。对。So if these are these other three things are the error term。

 so let'll say this is， you know， the amount of error I add is plus minus the absolute value of this quantity。

Plus minus the absolute value of this quantity， plus minus the absolute value of this quantity。

And then now I can do Kooshi Schwartzs again， I can say， look。This right here。Is that most？

The norm of f of x。Times the norm， the Euclidean norm， F of y minus F of y。

And this is at most right here。Again， similar at most F of Y。Times the norm of that difference。

 et cetera， and the same thing here I can do this is at most some norm。Time and norm。Okay。

 and the point is now if I take， let's say a gamma net， not an L infinity， but a gamma net an L2。

 then by definition。This is at most gamma。And this is attmost gamma。 and in fact。

 this is atmost gamma squared。Okay， do we not say there was a most epsilon at the sorry。

Did do not say it was the most epsilon at the top。 or that supposed to be gamma。 Oh， yeah， yeah。

 sorry。 So yeah， let's says， I mean， I'm gonna make it， I'm gonna set it to be epsilon。

 but let's' let me be consistent with myself。 It's gamma。Okay。So。

 and now what do I know about the L tune of F of x again， you know。

 this is basically at most one plus epsilon so this is， you know， it's roughly at most， you know one。

And this is roughly one， as well。So this whole thing is definitely， you know， F of x。

Dotted with F of Y， you know， plus or minus some like basically O of gamma。Because I have two gamma。

 roughly two gamma plus gamma squared of gamma。So I can set。Set you gamma to be again。

 some C times epsilon。So that implies that。That implies that this， again， is f of x plus dot f of y。

Plus or minus epsilon， which is exactly what I wanted。

 I wanted to basically be able to know the dot product dot product up to an additive epsilon error。

And now the question is， what is the size of this net？Again， you know， all these points。

 these x's and y's of mine， these are the these are the F of Es and the F of Ys Js。

 they have norm roughly1 one I most want those epsilon Okay。

 so really what I want to know is like the size of the net。We want。You know， an epsilon net。

 you know， basically gamma net， but gamma is basically epsilon， an epsilon net of。You know， the。

B L2 M of radius， let's say ones epsilon， This is the radius。So what I mean here is。

Take the ball in the L2 norm in dimension M of radius impulse plus epsilon。

 I want an epsilon net of that。And basically by this thing over here。This is the unit ball。

 this is radius1。But if you want to cover the radius one ball with， you know。

 covering the radius one ball with with like an epsilon net。

Is the same as covering you know the radius R ball with an R times epsilon net right if you scale up the ball by R and you scale up the net closeness by R。

 it doesn't change the covering it doesn't change the entropy number at all， right？

Does that make sense？Because in the scale down version。If things are within epsilon of each other。

 then if you scale up everything by R， then now they're within epsilon R of each other。

So the you know， the fact that the fact that we're looking at the one Bulls epsilon ball just means that we should scale up。

We should scale this epsilon also by one plus epsilon。

But epsilon times one plus epsilon is still basically epsilon。So， you know。

Bottom line is that if you look at。This， covering the entropy number of this ball。

 let's called this B， you know。B prime because the net B prime under the L2 norm。

With a quality epsilon， this is big O of like whatever epsilon raised to the dimension。

 which for us is M。 all of this is happening in dimension M。Because we're covering the f of x's。

 which are't dimension now so this implies that。嗯。To specify a point in the net。

 you have to tell me which of these one erupts onto the endpoints is it？😡。

That takes log of that number of bits so that's like。

O of M times log going Epsilon bits to specify a net point and there are n net points because there are n vectors that we're applying F2。

So that's its total bit length of the injection and that again， has to be omega。And k log in。

And then you get cancellations just like before。So that implies that M is at least。

Onener rhpson squared log and over log one of rhpson。Right。So this， by the way， is exactly you know。

 there was a lower bound improvement in 2003 by Nogo alone。This is exactly his lower bound。

 I mean the bound itself is the same bound he showed， but he did not actually use this argument。

 he had a totally different argument。Which I'm not going to show you today。Okay。

 but it's interesting that this totally different， you know。

 this totally different approach happens to recover the same exact bound。

 So now what I want to show you though is take three， which is even this log when uppson。

I want to get rid of it。收。😊，We just have to， you know it's。At this point， we're almost there。

 we just have to kind of。You know there's one thing from convex geometry that we need to know。

 remember I was talking to you about symmetric convex bodies and the fact that they're in correspondence with norms。

 we're going to use that now。Okay。But you know， you'll see we're going use in a very simple way。

 And now， you know， the hard part is just a matter of writing down everything we know and then。

kindind of leveraging as much as we can to get rid of this thing。 I mean。

 so so what what are we going to do， Okay， so let's worry what we know。Sa that。To， you know， decode。

Whenever we do these compression arguments and I say like we show that their existent injection。

 right that injection you can think of as an encoder， how do you prove that as an injection。

 you prove that you can invert it， namely that you can decode。The output of it。 So to decode。

 you know， we just needed to know。You know， basically。EI dotted with YSJ。嗯。Up to some add error of。

 let's say， I don't know，3 epsilon。For each， actually， we said two epsilon。

 I think it doesn't really matter。For each IJ。IfIf we know all these dot products up to this added error to Epsilon。

 that's enough to decode。And how are we getting that， we were saying， look。

 we're saying take this dot product， you know， like F Tilda。E1 transpose， so as a row vector。

F tilde E to transpose。 So it's a row vector up to F tilde。ED transpose。

So like put these as rows of a matrix。Call this matrix A。

 what are the dimensions of this matrix it has D rows。And M columns。And then multiply it by this guy。

Maybe myself。Which is F of YsJ。Right， and let's just call this， you know， this is by definition。

 let's call this VJ。 so VJ。Is this D dimensional vector？

So what we said basically is as long as you know。this should also be tillilda should be m dimensional。

AlW， which one。F， F FY。For YSJ， Yeah， this is M dimensionsal， that's correct。But VJ is deammission。

Okay， I guess technically I tilted the whole thing before， so these are all tilted。Oh。

 VJ is the whole product， So， VJ is like all the do products。 Yeah， they're D of them。

So really what we're saying is like we want to know VJ。For each day。It's the same thing， right？Okay。

 so we said that as long as we know VJ for every J， we're happy。That's basically what we said so far。

But notice that。That's that even tells us a little bit more than what we really need because we don't need to know VJ exactly。

 we just need to know VJ rounded to an L infinity net。Right， so we we actually。Only need to know。

Some VJ Tilda such that。VJ minus VJ tilde。An infinity norm is at most epsilon， right。

 because what are the entries of VJ？They're either between。Minus two epsilon and two epsilon。

Or they're between eight epsilon and 12 epsilon。That tells us whether or not I is an SJ。

So you know if we know if we know it only up to another additive error of epsilon。

 that means now it's between minus three epsilon and three epsilon。

Or between seven epsilon and 13 epsilon， that's still those intervals are still disjoint。

So we still can tell whether or not I in S。嗯。Okay， and then here's the here's the。

 I guess the the part really， I think that。Is maybe the least。UhYou know， the thing that， you know。

 maybe you wouldn't think of unless you know a little bit about this， you know， convex geometry。

Thinking to do is， look， let's define a symmetric convex body。E is equal to。The诶。你是。The column space。

Of a， in other words， equal to the set of like。The set of all vectors， A Z。Where Z is an RM。

this is a subspace of RD。And the dimension of the subspace。Is that most M because a has M columns？

Okay。And。Now what I can do is I can define a symmetric convex body K。To be equal to E。Interssect。

The L infinity ball。In D dimensions of radius， you know， around the origin of radius 12 epsilon。Okay。

So it's the intersection of this L infinity ball， which is a cube。

 so it's some cube of like side length 24 epsilon in every dimension。

And I intersect that with some M dimensional substancespace。

So now what I have is I have basically a lower dimensional you know an most m dimensional or a dim E dimensional symmetric convex body。

 which is K。So this is a symmetric。Convex body。Of dimension。At most end。And what do I know。

 I know that。For all J， VJ is in。Right。Because VJ is definitely an E。

It's equal to a times some vector。And it also has Elfinity or at most 12 epsilon。

 that's what we said earlier。And now here's the magic。

Rather than think about it as I want to take some Ellenfinette。Of quality epsilon。Indeed， mentions。

What I'm going to do is I'm going to take a k net of K。K is some set， it's a symmetric convex body。

I am going to cover it in its own norm。ok。😊，And I'm going to take a gamma net in the K norm and what's gamma。

 gamma is going to be a 12。Take a 112 net。Of K。In the canon。Okay。And then I'm just going to say。

 look， V Tilde is the closest。Point call this thing K prime， this is the net。

Vio is been the closest point in K prime。To V and K。What do I know。

 I know that v minus v tilde has an affinity norm at most epsilon。Because k， the body， you know。

 remember， I' remember the k norm。嗯。Another way to think about epsilon nets。

 instead of thinking about it is I want to take a subset of the points that covers everything。

 you can think of like I have this body K。😡，And I'm taking versions of it that are 12 times smaller。

 and I want to cover it with I'm going to cover it by translations of itself。😡，So like， you know。

 that's basically a square， I want to take smaller square squares that are 12 times smaller。

 and I want to cover it with these smaller squares that are 12 times smaller。Doest make sense。

 so right， so basically。The original square had side length of 12 epsilon or 24 Epsilon or whatever。

And now these small red squares have side length epsilon。Because I'm thinking a 12th net。

 I'm shrinking it by a factor of 12， does that make sense？对。

It's this case is's only like her conve body in this， think not on all of ourD。

 but just have this m dimensional sub exactly， if you view it as like in the subspace， it's an。

 it's you know， it's a dim E dimensional body in that subspace。It has volume in that substance。Right。

So like the net points are basically the centers。Of these red walls or these are the net points。

And I'm saying that everyone in the black square is close to one of these red points。

And what's the distance， you know， if I'm if this black point is close to that red point， then。

It has to have a infinity distance at most epsilon because that red box itself only has。

Radius Epsilon and Elfinity。So now what's the size？Of a 112 net of K in the k norm。And magic。

We can use this thing again。if you're covering the ball of a norm。In its own norm。

Then the size of the net is roughly one of epsilons in the dimension。Okay。So， that means that。

K prime。Has size。You know， O of。One over 112。To the dimension of the body， which is M。

Which is like o of 1 to the M。So that implies that to specify a point in the net。

You only need O of M bits。To specify。嗯。Each V J。So this implies O of NM bits total。Yeah。

 and that's exactly what we wanted right now you have Nm is omega。And K log n。系啱你嘅。

Exactly what I promised you to ends cancel。M is omega，1rup on S language。

There is a very slight issue here。There's a bug。So。

I'm going to be able to fix the bug on this slide and you know I left some space open on the right hand side。

 but anyone does anyone see why there's a bug here， it's not totally obvious。Any takers？I mean。

 you didn't resolve the D equals whatever it。 Okay there's that， too。 That's true。

 I didn't resolve that that I said D to be something very specific。

 And notice I haven't even used it yet， right， I haven't used the fact yet。

That D is specifically an over long run repon， why did I choose that？嗯。I mean， I did do， you know。

 earlier on we did have a log D over case somewhere and I said， look。

 this is roughly log n because D is this， but。I mean。

 I could have chosen there' was a wide range of what I could have chosen D to B to make that part of the argument work。

 why did I choose specifically and ofla or epsilon？

So let me let's just pretend for a second that we are the decoder right。

 we're given the injection applied to the point set。

And we need to figure out how to invert the injection。行。😊，So what did the encoder do？😡，The encoder。

 this is what？You need to know what the subspace is Yeah， exactly。

 you need to know what the subspace is right So what did the encoder do， What did the encoder do。

 The encoder wrote down this matrix a。He said， let me define E to be the column space of a and let me define the symmetric convex body K。

 which depends on A， depends on that subspace。And then then he you know he rounded to a net of that norm。

 but the point is the norm depends on the subspace， the subspace depends on F right。

 because if you look at the matrix A， it depends on F。😡，And F is actually really f sub x， right？

All we know is that each point set has its own embedding。

So F for this point set might be different for F for that point set。

Which means that the subspaces you get， the A's you get are different。

So the decoder who's trying to decompress， you tell them， okay。

 V1 tilde is the 17th point in the net。He's going to say what net。

 I don't know which norm you're using because I don't know which subspace。

Was used in the definition of the norm， because I don't know a。The decoder does not know a。

 so that's what we're going to fix right here。TheEnr。Also writes down A。How many bits does that take？

Well， a has D rows。And each row is a rounding in an L2 net。Which is an epsilon net。Of dimension M。

So D times。Ammilo went to rhpsilon。Bits。But and then I used the what D was D is and divided by law what erups along。

So， this is。Again， another an bits。So you know in total， I'm still only using O and bits。

So that now I'm really not now I'm really not lying to you， that really is， that's the end， okay。

So now the decoder can actually decodeder So so now the question is like。How do about what what if。

 what if。You know what if？D is not equal to n over1psson。So the easier case is。

That D is bigger than Nar obpsson。What if I want to show a lower bound in this case， that's easy。

Just take the set of points that's hard， we just showed that there is a set of points that's hard。

 take the set of points that's hard in dimension N over log in revs slide。

And just pad them with zeros until they have dimension D。This， I mean。

 you haven't changed anything about the points about the distance structure。

 so if the original point set it was hard to embed， this is just as hard to embed。

Still just as sorry。Case two。What of D is less than N overlo or epsilon？Okay。Let's say that。诶。

X is the hard point set， X is hard。It's in dimension。And it like website like。

Hard meaning that it's a point set where you cannot be jailed。So what are we going to do to x？

Let's just apply J to X。The claim is that F of x is hard。Where F is a jail embedding。So F of X。呃。

Has dimension。Oh of one over uppsilon squared。冇嘅。Right。And the point is like the proof。Suppose not。

Suppose。G。Maps F of x to some very low dimension。Beating jail。With good distortion。

Then G composed with F。Bes jail。For X。But that's a contradiction。Because we said that they'。

 you can't be jail for x， you can't go into lower dimension for x than J。That was our assumption。

 our assumption was that x is the hard point set。So basically what this argument lets you do is this box basically says。

We can get a hardy points set。For any。D， which is at least some constant times what are Epsilon squared log。

Of course， once D is much smaller than that。You're not going to be able to prove a jail or bound why because you can just take the identity map。

If the original dimension of the point set was five。You're not going to be able to say， oh。

 there's no way to embed this five dimensional point set better than one ofson squared log n No。

 you can just do the identity map， the identity map map it back to five dimensions。

With no distortion whatsoever。系。So， yeah。Essentially， this is the best you could hope for。嗯。

Any questions？So that's really it， you've seen everything there is to see about the jail organ。

So now I want to talk about。You know， phase two of this scher。We're just speeding up jail。And。😊。

You know， the original jail。In 1984。Is random projection。So what does that mean？You take。

Take a random。M dimensional subspace。耳机。And project there。How do you do that， how do you actually。

 you know， if you want to actually like write code and implement this， how would you do it？

Here's one way to do it， you know I basically need to take a random basis。

 so I need to take M vectors or M random orthoormal vectors and RD。😡，So how do I do it？

My first vector， you know， they're in RD， so they're D dimensional。The first vector。

 I'll just take some random Gaussian vector。Okay。Gaussians are rotationally invariant。

 so I mean you're equally likely to get any angle， you know。the direction， I mean， the magnitude。

 the L2 norm of the vector is a random variable。But the direction it's pointing in is a uniformly random variable over the sphere。

So you take this G1， which is ID Gaussians， and then you just normalize it by its norm。

So you remove the randomness from its norm by normalizing now you actually just have a random point on the sphere。

 so there's your first basis vector。😡，Now what you'd like to do is you'd like to take another Gaussian vector。

ok。But the problem is， of course， that it might have some。You know。

 it might not be orthogonal to the previous one。So you just project that out。You know。

You remove its projection onto the first vector so you dot it with the first vector that gives you a coefficient。

 you subtract the coefficient times G1， so this is like the normalized version and then you normalize by more。

Et cetera。 So basically what you're doing is you take I ID。Gaauussian vectors。You know。

 identity covariance matrix and dimension D。And then you do what's called the O Graham Schmt。

Graam Schmidt just means。You know， you authornormalize them。Okay。

 so what does that mean at the end of the day， This is going to be a。Dense。Unstructured。

And a random matrix。Which means if you look at the map Z， it's mapped to Pis Z。Is super slow。

And I should say， this matrix is's called this matrix A。

Then eventually you're going to take m of them， eventually pi is just going to be a transpose。

You know， maybe appropriately scaled。So that's the original jail matrix。I may not say super slim。

 I mean I want to I don't want to use superrelatives unnecessarily， but you know。

 I just want to say that。Zta Pis Z is， you know， is。Dense， you know， matrix vector multiplication。

Whiicie I was like。Basically M times D time。You have an M by D matrix， it's dense， it's instructed。

 you're multiplying it by a D dimensional vector that takes time m times D。So， you know， naturally。

 there's a question here of can I do that faster， can I get the same kind of jail guarantee with a faster embedding method？

And。If you think about， you know， the motivations for JL， one motivation is like。

I have this high dimensional point set， I want to run some algorithm on it like clustering。

 nearest neighbor search， whatever。If I just run the algorithm on the high dimensional version。

 it's going to be slow， it's going to use a lot of memory， whatever。

 but let's say it's going to be slow。So let me first project the data down a low dimension。

And now my algorithm is probably faster because it's operating a lower dimensional stuff。

So if you think about it， there are two parts to this。Part A is actually do the embedding。

And part B is now run the algorithm on the lower dimensional version。So yes。

 getting the dimension low helps part B。But， you know。

 it's not going to be worth it if part A is itself just as slow or slower， you know。

 ideally I want both parts to be fast， both the embedding time and then running the algorithm on the Lord Menstrll versionrg。

So we've nailed the。The dimension that's achievable， we've basically nailed Part B。

 We know that you can achieve one ofpsson squared log n and there there are some point sets so and then we've nailed in the worst case。

 there are some point sets where you simply cannot do better than that by a constant factor by more than a constant factor。

So now the question is， can we now do something to improve Part A。

 which is speeding up the actual embedding？So the history behind this。

First there was Oleyocus in I want to say 2001。Sped up。The map Z gets mapped to Pi Z。

By a factor of three。Without。Sacrificing。不 sorry点样写。So what do I mean by that？You know。

 pi is a matrix。What he did basically was， you know。

 he looked at what was the target dimension that the best analyses out there could prove。It wasn't。

 you know， you look at even the constant factor， it's not just big O of Vo uppsson squared log n。😡。

he figured out like what is exactly the constant hidden in that big O in the analysis。

And he showed that you can achieve that same constant。

While making it so that the majority of the matrix is actually0。 In fact。

 two third of the entries are0 in expectation。 So what he did was and a pi I J。Was。So plus minus1。

With probability， you know。One third。Zero with probability2 thirds。

And you have to scale by something to make the calculations work out， but you， scale by something。

Right here， I think for him S was basically M over3 something。So with probability one over six。

 you get a plus one with probability one over six， you get a minus one， so probably a third。

 you get either plus one or minus one。😡，And then with probably two/ third， you get a zero。

So in expectation， two3 of every column of this matrix is zero。Of course。

 you know that's that if you just want two thirds of the matrix to be zero。

 that's trivial to achieve if you're willing to blow up M by a constant factor， right， just tack on。

 you know， instead of making it m dimensional， instead of making it have M rows。

 making it have three M rows。😡，Where your last two Ms， you just make it all zero。Okay， yes。

 now two thirds of your matrix is zero， okay， but you haven't really done anything。But with him。

 he actually kept M to be exactly the same， even up to the constant factor。

And was still able to sparsify the matrix by a factor of three。

So that's that's really where the benefit is and keep in mind now this why is this useful。

 keep in mind that again， just a fact about matrix vector multiplication。

Pi times z is equal to the sum I goes from1 to D of Z times pi I。

Where pi I is like the I column of the matrix。So the point is now， you know。How much does it。

 you know， you're basically keeping， you can think of it as you're keeping m counters around。

You initialize it to zero。And in a for loop， you're adding Z times pi I to your counters， right？😡。

Does that make sense？You keep adding this in to your M plans because this is an M dimensional vector regulator。

So if only d over three， sorry， if only m over three of the entries of pi。Of pi I or non zero。

 then this takes time。Yeah好先息。Takes time roughly， let's say， M over three。To add。之埋。Encounters。

So you're kind of saving a factor of three to， right mean， of course。You have to be careful， I mean。

 depending on how this is being implemented if you can do。你心。

P parallelllel operations on your computer， then maybe this doesn't really matter to you。嗯。But。

 you know。This could matter in principle， depending on the architecture of the machine that you're doing this on。

Okay， so that's that just was the first person to give kind of anything on trivial。嗯。And after him。

 there was Ilo and Chaiseelle。In 2006。And they were the first to give an actual asymptotic improvement。

So they could do Z gets mapped to pi Z。In time。O of D log D。Plus， M cubed。

So if you think of M as small， M as a target dimension。If you ignore the M cubed。

 this is nearly linear time in the dimension of the vector Z。

 so it's like what better could you hope？To achieve。嗯。

We going this is called the fast ju interest transform。Fast。撞线。Lin' restaurant。Play FjLT。

We are going to talk about this， we might not get into it until Wednesday。😡，But you know。

 roughly roughly with this。Schemes does， as it says。Okay。

 they say like if my vector is very well spread around， if Z is very well spread around。

 meaning like。Its mass is not fully concentrated in one place。

But it's masses spread around so let's say all the entries are the same or close to the same or something like that。

 then they have a matrix pi that works it's basically a sampling matrix who sample entries from Z。

Of course， a general vector Z。Need not be well spread around。

 it could be a standard basis vector you could have all your mass and one coordinate and everything else is zero。

So what they say is。Our pi is actually going to be a product and a few different pies。 And the first。

 the first matrix we're going to hit Z with is going to be a random matrix that with high probability spreads the mass around so that Z is。

After you hit it with that matrix， it's not it's with high probability。

 not concentrated in just a couple of coordinates， it's spread around。

Then they say now that we've done that， then we can apply the next matrix。

And then that will work on this well spread vector。

 so our final pi is just the product of these two matrices。Okay， so you look at this and you say。

 well okay， what's the down side， the down side is wait。

 what if Z was actually originally super sparse？For example。What if Z only had one non zero entry？

Then。Doing the dense matrix vector multiplication is actually not even that bad if it only has one nonzero entry。

 that's basically just telling me some column of pi。

 so pi Z is just ZI times that column of pi times pi I。So it's very fast， it's only it takes time M。

To compute Pi Z。So， but if you look at A Chielle what they're saying with the FjLT is， you know。

 I don't like sparsity because it kills the correctness of my procedure。

 so I'm going to densify the data first and then I'm going to operate on the densified data。

 but that could be a serious downer for runtime， like if your original data set was very sparse to begin with。

I don't want to densify densified is just， you know， making the data。

Even more complicated going it's going to take now more time to do an embedding on it。I would like。

To take advantage of the smartsity。To do better than this。

And kind of the first paper that showed that you can do something with an asymptotic improvement for this。

Was。Ds Gupta Kumar and Char。This is 2010。And， you know， for people who don't know you know。

 apparently and I don't speak Hungarian， but if you ever meet someone who speaks Hungarian or whose name is Hungarian。

An S in Hungary it is like an S in English， so it's not Slos， it's Charlo。And if you see an S Z。

In Hungarian， it's like an S in English。Which is， I guess。

 contrast with like Polish where it's an SZ in Polish is actually like a shot。Anyway。

 just a random fact。So just keep to Kmar and Charlotte for the first to give some asymptotic improvement for sparse vectors and then kind of the state of the art bound is due to myself and Daniel Kane。

And then we show that you can do Z gets mapped to pi Z。In time， basically。Oh of。M plus。

Epsilon M times the number of non zero entries in z。 So Z not for me is the support size。

 it's the number of non zero entries in Z。And the way that we achieve this， let's let me call this S。

What we show is that。Can get a jail transform。With S。M zeros。Her column。So pi itself is sparse。

Like occalopptus， but even Sprser occalopptus made it so that only a third of the entries are non zero now we're saying that only an epsilon fraction are non zero right so epsilon can be something very small。

😡，And this is called the sparse。John Soon and Strau transform。Or the SJLT。And actually。

 what is the matrix， the matrix is， I'll draw it for you。So we look at each call of this matrix。

You basically break it up the rows into blocks。Asked blocks。And in each block。

 you're going to have a bunch of zeros。And then， a single one。And then a bunch of series。

And that one is in a random location。I claim that you've seen this matrix before。

So what is this matrix？It's like the coherent matrix for a code。Yeah， okay， good， yeah。

 so it is it is related to the。It is related to like how to take a code and convert the code into an incoherent matrix from the homework。

But you know， a code could be， you know a code is like a very a code could be deterministic right a code is a deterministic object。

 it's a collection of vectors that has some overlap properties right or distance properties。Here。

 this is not deterministic， I'm choosing where to put the ones randomly。😡，So you can say yes。

 it's like a construction of a random code。But I claim that exactly this。

 exactly this kind of distribution is one we've already seen in class through it's like the countman sketch Yeah。

 it yeah， so it's exactly the count sketch。Oh， good what I wrote you're right What I wrote is the countman sketch because I have a typo。

It should be a plus minus1。Okay， so now it really is the count sketch。Right。

So each one of these non zeros is a random sign。So what we show is that the k sketch itself。

Actually provides the jail guarantee。Where。M is O of we're going to do it。

 We're going to prove it for a distributional jail。

 which implies jail M is one of upson squared log whatever delta。

And S is going to be O of like one of our Epsilon log whatever Dta。Which is oh， Epsilon him。

And there's a lower bound。By myself and Hui Wen。W says that。There exists point sets。Suchし that。

And at most， you know。Oh one or upson squared log n。Implies。Some column。Needs。At least。

Omega one of epsilon log and over log one of Epsilon non zero trees。In other words， like。

There are point sets where if you try to embed them with sparse matrices。

 if you try to tailor a sparse matrix just for that point set。

 it doesn't even have to be a random matrix， it doesn't have to count sketchch。

 there simply isn't a sparse matrix with sparsity better than this。😡。

Which is almost what you would get from this SjLT up to this log one ups long term。

 so the SJLT is in the worst case。neearly optimal in the verrsity I achieve。Okay。

So let me show you now how to prove this， that's I think that will take up the remainder of the lecture and then we can talk about the FjLT and move on on Wednesday。

So before I tell you how to prove basically what I want to prove you to you is not the lower bound。

 but what I prove you is the upper bound， namely that this works。Okay。

Any questions before I prove it？So let's prove it SJLT analysis。

So let me define some random variables。Eta are。Let's just say that。

The pi R is equal to one over root s times。Eta R I times sigma R I。

 where Eta R I is either a 0 or 1 and sigma R I。Is。In minus11。So what I can， you know。

 I just want to， this is just makes it easier notally to carry out the proof。

What I want to imagine is that pi actually is a completely dense random sine matrix where the entries are sigma R I。

 but then I masked it with with these a does。 So if ada is a 1。

 I actually keep the sign If a does a0， I zero out the sine you know。😊。

I can express the matrix this way， right where8 as an indicator random variable telling you whether whether that entry is zero or not。

 does that make sense？And then if you look at。And of y， which is equal to pi times z。

You look at the error random variable， so let's say now capital E is for error。Is defined to be。

Pi Z L norm squared。Minus z out times squared。And you know， without loss of generality。

 I can just say let's say Z is one。Because if it preserves vectors of unit norm。

 it preserves vectors of any norm because it's a linear map。是。in this thing here， what's all right？

What's R， so like R remember pi is an M by D matrix， so like。R is between1 and M。

And I is between1 and D。Does that make sense？So PRI is just like the RIF entry of pi。

Does that make sense。 Oh， I thought it was like R sub I， Sorry， sorry， R comma I。

I just don't I have to keep writing to commas。ok， so。This thing here。Is me。So yeah， so you can write。

 it's the sum overall I from1 or R from1 to M。Of pi Z R squared， which is the sum R goes from 1 to M。

There's a1 over root S squares， there's a1 over S。And then now the sum I goes from1 to D。Ata R。

 Sigma R， Z squared。Okay。And this is equal to， you know。I write it like this， one over S。

Some R goes from1 to M， some I goes from1 to D。Of。Eda R I squared。Sigma R I squared， Z I squared。

Plus， the sum goes from R goes from1 to M， some I not equal to J going up to D。Of ata R， Eta Rj。

 Sigma R， Sigma Rj， Z I， Zj。Okay。Now let's look at this。Let's take these two summations。

And like swap their order。If you swap their order you get。Some eye goes from one to D。Z， I squared。

Sigma R squared is1， so that doesn't matter。A to R squared is the same as a to R because it's a 01 random variable。

 it's a 01 variable， so if you square it，0 squared is 0，1 squared is 1， it doesn't change anything。

So now here you have the sum overall all R from1 to M。Of A R RI。What is this？Oops。

What is this quantity？Can someone tell meIs it one， becauseuse there's just one in each column。No。

There's not one in each problem。I guess it's S。 or're S in each column， right？But yeah， close。

 there's not one in each column， there's one in each block。And there are S blocks。

 so there are S of them， so this is S。So remember now there's this one over S。

And then there's this S， so that cancels。So， this goes away。And the sum of Z squared。Is one， right。

But remember， there's a minus one here too。So that cancels。So that just goes away？

So this implies that E is equal to1 over s， some a goes from 1 to M。Some I now equal to j。Of Ada R I。

 Ada RJ， Sma R I， Sma RJ， Z， I Z2。Sounds like a mouthful I know， but that's what it is。嗯。

And by the way， I mean， it's interesting because if you look at oalopptus' original proof。

Or just like his construction。I mean， it's somewhat similar to this， by the way， I should say。

So the count sketch indeed works another thing you can also do and the same analysis we're about to do shows it is don't do the count sketch just like。

For each column。Pick S entries without replacement。And make those S entries be random signs。

 so there's no more block structure， it's just simply S locations chosen without replacement randomly。

Make those be random signs and make the rest be zero。

You can prove via the same analysis we're doing now that that also works。😡，ok。

Which is very similar to occleopptusocccleopptus is basically andocccopptus says in each column you know。

 pick the entries independently decide whether or not they should be， you know。Zero or non zero。

And make the sampling probability be such that you expect S non zeros。😡，Whereas here we're saying。

 I don't just want to。I don't just want to expect S non zeros。

 I want to enforce that there are exactly s non zeros。Right。

Because I'm sampling S without replacement， I'm enforcing that they're exactly S。

That actually makes all the difference。You can prove that if you actually do actually up to this version。

Where you just IID choose whether to make it zero or non zero。

 you actually need S to be1s on squared log whenever delta if you do that。

But if you make if you enforce this， then you can actually save on s by factor of epsilon so it's just the way it's just the way that these these random variables behave you know that their taildowns behave that somehow this very slight tweak。

Is like all that it takes， but it's actually necessary to make the treatment。

In in the version with the fixed number of ones is better。Oh no so yeah。

 so the version of the fixed number of ones， which you know you can either choose without replacement you do or you can do it like the count sketch。

 the count sketch also has a fixed number of one plus minus ones per column。

Those do strictly better than if you make it so that you know the entries are just IID0 and non zero。

😡，Because the problem if you do that is like basically。I mean， I'm not。

 I haven't convinced you that it's a problem， but you can see why there's a difference already in the analysis because for us here。

😡，The diagonal terms from that double sum perfectly canceled out with the minus one。😡。

RightAnd the only thing that's left is the off diagonal terms where I is not equal to J。

But in the Olyopus version， the diagonal terms in the minus1 do not perfectly cancel out。

Right because you only you only expect there， you only expect them to cancel out in expectation。

that diagonal gives you one， but there's variance there and it probably is not going to give you what exactly。

And if you try to understand the deviation there from the diagonals。

 that turns out to kill you already。😡，Okay， so I'm not going to prove that here。

 but that that's kind of an interesting thing where you might not you might not have a priori expected that there would be a difference。

But it turns out that there actually is a difference。Okay。so。Let's go on to the next。

Board Commission， let me switch back to black。So we just said that the error random variable。

Is1 over s some R goes from1 to M some i not equal to J of a to R， A to Rj， Sigma R， Sigma RJ， Z， I。

 Zj。And let me remind you that。We have the Hanen W Equality， which we're going to use Hanson Wright。

Says that。For all I'm going to write the I'm going to write the norm version remember tail bounds and norm bounds are equivalent。

So it's for all p gradient equals to1。If you look at the p norm of sigma transpose a sigma where sigma has plus minus ones。

 random plus minus one is the p norm this at most。Root P times the Frbeius norm of a。

Plus p times the operator row of a。Just remember that。If you look at a random variable Z。

Its P norm is just defined to be the expectation of z to the p to the1 p。So E。

I can write E as sigma transpose and then I'll call it， you know， I'll call this matrix。A sub。

Let's call it a subs Z eta or let's call it a sub Eta。识啊。So it depends on A and also depends on Z。

Where。A有 a。A is the matrix which looks like a1 over s here and it's a big block diagonal matrix。

And let me call it， let me call this matrix。Let's say Z1 Z1 transport is Eta。诶其数。You know what。

 let me not write it like this I was going to write it as。A Eta 1， A Ata2。

 and then the number of them is S because there're S blocks。Or actually M。A A to M。

 each one of these is D by D。So the big matrix， it's MD by MD。And what are these matrices。

 if you look at A A to R。And you look at the I J entry of this thing。

It's equal to zero on the diagonals if I is equal to J。Otherwise， it's equal to。ZI。Ata RI。

Z Zj a to Rj if I is not equal to J。So it looks a lot it looks a lot like。You know， I'll call it。诶。Z。

II'll invent some notation。Okay。So this a funny dot product thingingy。What I mean by that is。

 know these are two vectors， there's a vector Z。😡，There's a vector a to R， which is like ata R1。

 ata R2 up to ata Rd， it's also a D dimensionsal vector。

I'm going to take these two vectors and entry wise product them。😡，Okay， which is basically a mask。

 Eda is a mask vector right it zeros some things out， it keeps other things。😡。

So I apply this mass vector to Z， so it zeros out some entries of Z， it keeps the rest。😡。

And then I take that masked version and I take Zzi transpose。And then I zero up the diagonals。

Does that make sense？That's what AA R looks like。Okay。😊，Questions about this？Okay。

 so what do we need to understand？Me need to understand。

The Frenous norm of A Eta and the operator norm。And let me also， you know， let me。

 there's two sources of randomness here， Sigma is random， but so is Ada。Okay。

So let me take the LP norm， let's look at sigma transpose。诶。A Eta sigma。

 let me think the LP norm with respect to both like。In other words。

 I'm taking the expectation with respect to both。Eta and sma。Okay， so this I can write as。First。

 I'm just going to do like。You know， you can imagine here like over here in this definition in the top right。

 you know， I'm taking there are two sources of randomness， I'm taking it over both。Sigma and Eda。

Z here has been rotated so that it's not sparse， right？Onces we rotated Z？So it's not sparse。

What do you mean by Z is not spa Z is whatever vector I'm trying to embed？

Right well I thought we were doing there's like the preprocess step where you make sure that the support is not too small Oh yeah no no no no so yeah sorry if I it goes confusing about that right there are these two approaches there's this approach and this approach Oh I see okay sorry I launch Zelle does that pre processing。

The sparse JLT like adjust this is pie， that's it， pi is the count sketch。咁一。So。

So basically what I want to say is like I'm going to take the expectation over Sigma first。

And then I'm going to apply Hanson right I'm going to get an answer that depends on。AEda。

 and then I'm going to take the expectation over Eda。So let me write this as you know。嗯。

Let's right it like this。Sigma transpose a Eda。识啊。LP Sigma， and then like LP Eta。That makes sense。

So let's first just focus on what happens when you so now like Ada is fixed in there and I can just apply a Hanson right to that。

行。So， you know， next board， and let's go to the next board。嗯。So this is at most。

Up to a constant by Hanson Wright。嗯。Rot P times the。For me it's norm。咁 a a啦。

Plus p times the operator of AEta。And then LP over Eta， take gras over Eta。

And then I can do you know triangle inequality and I can say， look， this is at most。Root P times。

Ada forenous norm。Help your Rada。Plus P times。This thing， operator norm。

So let's first do the operating arm because that's， I think a little bit easier。So。What is remember。

 if you have a block diagonal matrix？Then the operator norm is the maximum operator norm of any block。

😡，So we just have to ask ourselves like， what's the maximum operator of a block？So。ふ。

The soup over all acts of unit norm。Of some like x transpose。A8 to x。嗯。Is。Equal to。嗯。I actually。

 I don't want to say it， you know， I I can just write， let's just write this。

This I think will be even easier。good look a Eda。Is just actually equal to。And I by the way。

 there's you know， the way I define Aa is there there is this one over S that's on the outside of everything。

So A8 to R。诶。入边。I guess， unfortunately so I didn't put one of us in the definition of AAR。

 so we just have to remember it's a divide by S of the end when we do all this stuff。

But if you look at A8ta。A Ana R here。This is equal to Z， you know， funny dotty thing。

 a to R transpose。Z， funny dotty thing A to R or sorry。Okay。

 but then you have to subtract off the diagonal minus。😡。

The matrix that has like every all the entries on the diagonal。Which here is you know。Z。

1 squared Eta r1， Z2 squared Eta R2。All it is like ZD squared a RD。So this is what A A R is。

So the operator norm。Is the upperer of this？Which you know， you could use triangle inequality。

 you could even take a factor of two by doing something slightly fancier but let's use tri inequality。

Btorial inequality， this is at most。The operator arm of Z dotty thing a to R。

 z dotty thing a to R transpose。Plus， the operator on of this square matrix here， the Staular matrix。

What's the operator norm of this， it's basically when we proved jail before。

 we basically ran into something like this is a rank one matrix。It has a single non zero eigenvector。

 which is Z funny dotty thing AR， so it's operator norm。😡，Is the L two norm squared of that vector？

Which is at most ultimate square root of z。And this is a diagonal matrix。

 so its eigenvalues are just the entries in the diagonal。

 so this has operating at most z l infinity norm squared。😊，So this is at most one。

 this is at most one， so we've just shown this is at most two。Right。

And then remember there's a1 over S that you have to remember。

 so this you know this is basically always at most two over s。

So you don't even need to consider the fact that A is random in this part。

We're going to use that for the Frbeia Smart part。The fact that Ada is random。

 that for the operator room part， Ada didn't even need to be random。Okay。

 now what about the Frbenous norm？Okay， so。The Frbei storm squared。Hey， Ada。

For being is norm squared。Is equal to。1 over S squared because there's a one over S over， you know。

 on the outside。 So square that sum。R goes from1 to M sum I not equal to J。Of Z I squared。Zj squared。

Eta R I， Eta Rj， where you know again， the es should be squared。

 but it doesn't matter because it's a  zero1 variable so squaring is0。

0 squareing1 is one you don have to square the as。Now notice that Z squared Zj squared doesn't depend on R。

So you can just take these。And move them in here。So this is one over S squared。

Some a goes from one to app， a sum。Some sorry some I not equals to J。Yeah。

 let's also reverse the order of summation， I guess I should say， so reverse the order of summation。

Some I not equal to J Z squared。Zj squared and then like a sum of R goes from1 to M。Of88 R，8 RJ。

And let's just call this thing here now like QIJ。What does QIJ mean in words QIJ is like if you look at。

😡，The I column of the matrix pi and you look at the JF column。

How many non zeros do they have in common？How many rows do they both have in common as being non zero？

And then now if you look at。Okay， so let's just let's just reche what we have。

 we're almost out of time here， but I can basically tell you how to finish this。

So what I said is ata a Eta for beingi storm squared is equal to the sum1 over s squared。

 the sum I not equal to J of Z squared to Zj squared。Q I j。

And what we're interested in is we're interested in Eta Frbeius norm。LP Ata。

What does that mean that means？The expectation。诶 sorry。That means the expectation。Over Ada。

Of this Forvenous norm。Raise to the P of power， all to the one over P。I'm just going to view that as。

I'm just going to view that as you know。This is actually like。The square。Raised to the P2 with power。

That's the same thing。And then raised on the outside to the。2 over P。To the one half。

So a lot of funny a a lot of funny acrobatics here。

 but basically the point is this is the same thing I was basically what I'm saying is this is now。

诶 a的。For being a norm squared。And then L P over 2 Eta。

So I have PSV at least two so that this is still a norm and then I then I can square root it all at the end。

 so I don't have to worry about the square root until the very end。

So now the point is I basically want to know the norm。

Of the from arm squared and then I can use triangle inequality。

 this is at most so I have a one over s squared but there's a square root on the outside so this is one over s times。

The sum I not equal to J of Z squared， Zj squared， and then the norm of Qij。

That was just triangle inequality and using what I wrote down as the Permed norm squared。😡。

And then I'm not going to do it， but the point is。😡，What is QIJ。

 what can you tell me about QIJ it's basically like。😡，A binomial distribution almost， right。

 because it's like， you know。I have these M trials because there are M rows。😡。

And I'm asking of these M rows， how many times do I have a non zero for both I and J？

What's the probability that for a given R？😡，I have what's the probability for we given R。

 I have a non zero for both I and J， it's roughly S over M quantity squared because they're S non zeros out of Ms。

 so it's S over M times S over M。😡，Which is S squared over m squared。

So what I'm doing basically is I'm looking at this looks a lot like the binomial distribution。

With parameter S squared over m squared。Where I' know。

 I'm summing up Bernoulli's P where p is S square where m squared， and I'm summing at M times。

QIJ is roughly a binomial distribution like this， does that make sense？So again。

 I'm basically out of time， why is it not exactly a binomial distribution。

 it's not because they're not independent， right the Adas are not independent。😡。

You know that there are exactly S per column。😡，So for example， if you know that。You know。

 rows number one， two， three， four， five， six both are non zeros for I andJ。

Then that decreases the chance that the future rows are both non zero because there were less of them。

 there was only S total。😡，Right， so it's not exactly a binomial distribution。

 but you can show it's it's not too hard to show I'll put it in the notes that。

The moments the moments are still bounded by the moments of a binomial distribution。

Then you try and figure out what are the moments of a binomial distribution？😡，You get something。

 you plug it in and you get a bound。😡，Okay， so then you're done。

 you have a bound on the Frenous norm moments， you have a bound on the operator norm。

 you plug it into handsson right， that gives you a bound on the moments of the error random variable。

😡，And then then you plug that bound on the moments of the error random variable into Markov's inequality。

 right so now you can set P。😡，Remember now the probability that the error random variable-。

 this is the last thing I'm going to write before I let you go。

 the probability of the error random variable is bigger than epsilon because what you're trying to bound is at most。

😡，It's at most。1 over epsilon to the P times the P norm。😡，Rised to the P， is exactly。

 this is just Markov。And then now that you've bounded this thing， that's what we've just done。

You can plug it in and you can basically get exactly what I told you。😡，And you know。

 at this point it's just really a calculation and we're out of time anyway。

 so I'll put the exact details of that calculation in the lecture notes。

 but that's all there is to it。😊。

![](img/516e90b646ce0b30b79b92b896ebe8fd_2.png)

Any questions？