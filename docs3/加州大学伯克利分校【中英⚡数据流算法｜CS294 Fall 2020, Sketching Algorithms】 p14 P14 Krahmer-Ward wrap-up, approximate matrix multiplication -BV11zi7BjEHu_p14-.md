# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p14 P14 Krahmer-Ward wrap-up, approximate matrix multiplication -BV11zi7BjEHu_p14-

![](img/21349bf6154bf1852ff7c73541898ba9_0.png)

Okay so today， in the beginning of lecture， I just want to finish off the proof of Crrame Award。

 which we started last time。It has some interesting ideas that we're going to use later when we talk more about compressed sensing。

And then after we do that， we're going to start talking about randomized linear algebra kind of using sketching techniques to speed up things like approximate matrix multiplication。

 least scores regression， lower rank approximation。K means clustering， et cetera。

 sos that's where we're going for the next couple of lectures。As well as the end of this lecture。

So if you remember last time last week on Wednesday。

 we were talking about the fast Johnson linen Strau transform。

And there the matrix looked like S times H times D where D was this diagonal matrix with signs in the diagonal H was the hadamar or discrete Fourier transform was a bound orthon system。

And S was a sampling matrix。Right and as I mentioned last time。

 the original jail proof for fast jail analysis said， look。

 if you condition on HD being nice then sampling works。

 what did nice mean in that in the AC analysis and the e cell analysis nice meant that。

HDZ has small efiny in arm， it spreads out the mass。So that no one coordinate has too much mass。

And Crramer Ward said， wait a minute， we actually have an idea to analyze it completely differently and they were building off of an idea from I and Liberty in 2011。

 but Crraman Ward said，🤧嗯。We're actually going to do the conditioning in the other way。

 we're first going to condition that SH is nice。And then once we know that S is nice。

 we can argue that if you throw on the D matrix， the diagonal signs。

 that's going to give you the distributional jail okay and what was nice there nice was that。

Pi satisfied the RIP。So pi satisfies。Something like you know epsilon， comma。Some constant oops log。

Whatever Delta。R I P。I don't know why it's not letting me right up here。Okay， so。

Right was it so here this is think of this as this is going to be my like 2 k。

What does it mean to be KRIP， it means that pis preserves the norm squared of any case parrsse vector。

 so for any case parrsse vector Z pi Z L2 norm squared has roughly the same norm as z L2 norm squared up to a one plus or minus epsilon。

So this is a completely deterministic property。We're saying that。

Pi preserves the norm of every case bar vector， actually every two case spa vector simultaneously。

Okay。😊，Okay， good。Last time we said， look。You know what we're doing， so this implies that。

Pi D Sigma gives distributional jail。That's the theorem。So that's what we're trying to prove。

 so we're trying to prove that for any for any unit norm vector Z。Pi d Sigma z squared。

 it has roughly the same norm z squared。Which is one， so it has more one， one write upilon。

And we started off the analysis last time by saying， look， d sigma times Z。What is that as a vector。

 the I entry is sigma IziI， so it's the same thing as Dz times sigma。Okay， and then I could write。嗯。

I could write。Pi D Sigma L2 norm squared as。Sigma transpose x Sigma where x is this matrix。Okay。

Where I basically just partition various parts of X。Based on the sortrded order of entries of Z。

 remember that I made the assumption that I reordered。I reordered the indices。

I reordered the dimension so that z1 is very equal to z2 is very un equal to but equal to zb。

And then I also defined。If I look at Z， it's some vector。The first K in trees are Z1。

The next K entries are z2， the next K or z3， et cetera， so all of these blocks have size exactly K。

And then when I look at the matrix right so I mean this thing here。You just expand it that thing is。

Signma transpose。嗯。D Z pi transpose pi D Z sigma。 So there's some matrix X here， right。

And what I did is I wrote down that matrix， it's a D by D matrix。And I just partitioned its entries。

 so there are the entries that are the kind of K by K blocks on the diagonal。

 so each one of these blocks is K by K。And kind of the unit of all those blocks is what I'm calling the matrix A。

 so in other words， a looks like this。😡，A is kind of all these entries in the diagonal blocks and everything off the diagonal is zero。

And then B is the matrix where。诶。I don't exclude that， but I include this， so this is B。

And then kind of everything else is zero。Right so I kind of highlighted in this picture where I defined x。

 what part is B， what part is A， what part is B transpose， and what part is C。So A is the diagonal。

 B is the first kind of first k rows except for the diagonal block。

 B transpose is obviously the transpose and C is everything else。And we're going to say， look。

 via this decomposition， I write sigma transpose a I can write Sigma transpose X Sigma。

 that's the thing we're trying to understand， I can break it down as sigma transpose a sigma plus sigma transpose B sigma。

Plus sigma transpose B transpose sigma。Plus dema transpose C sma。

 right I'm just using the simple fact that x is equal to a plus B plus B transpose plus C。

And then we're going to analyze these separately， we're going to say， look。

We'll show that with high probability。We have。Sigma transpose a sigma is like one plus or minus epsilon。

 Sigma transpose B sigma is plus or minus epsilon。Sigma transpose B transpose sigma is plus a minus epsilon and Sigma transpose C transse C sigma。

It's just very excellent。So these things combined。Imply that。Pi d Sigma Z Lt norm squared。

Is one plus or minus of epsilon with high probability， which is like exactly what we wanted to show。

哎。So that's what we're wrapping up today。I did show you already that。On Wednesday。

 I proved this already。And if you remember， this was completely deterministic as long as P satisfies RIP。

This holds with probability one， in fact， the fact that sigma is there doesn't matter at all。Okay。

 so well， just today we're going to finish。Today。Willll finish。The other three。Then introduce。

Kind of sketching for linear algebra problem。Sketching for a numerical in your algebra。Okay。

 so before we attack these three right here， any questions？Okay， no questions， so let's get to it。

So now we're looking at Sigma transpose B sigma。And just a reminder。B is this part of the matrix。

so it's just that。That top part。Where you ignore the top， you ignore the top left K by K block。

 but then you take the rest of the。K by n minus K region。你。So。Symmetry， so let me define。Okay。

 but first of all， sigma transpose b sigma is equal to。嗯。The sum over J bigger than one。

Of sigma 1 transpose。呃。DZ1。Pi 1 transpose。And then pi J， DZ J。smay。不这。And you know。

 just to make this easier on ourselves， let me just define。Kind of you know sigma like Z。

 when I say z minus1， what I mean by that is。Take the first block of K things。

And zero it out and keep everything else。So this is the same thing that was basically the sum over J bigger than one。

Of ZJ。And I can define。Sorry， I can define。I can define what pi minus1 means the same way withigma minus Sigma minus1 means the same way。

 exactly。对。不觉。So this is equal to sigma 1 transpose， Dz1， pi 1 transpose。Pi， -1。D z minus1。

 Sigma minus1。Okay。And let me just say that， let me just make a definition now。嗯嗯。那。

I'm just going to call this whole part。Yops， I'm meant to do that in different color。

I'm just going to call this whole thing。I first of all， what is its type？

This is a vector right so if you just look at the leftmost thing right Sigma is a D Sigma1 is a D by one vector so Sigma 1 transpose is1 by d。

And Dz minus1 is a D by D matrix， so altogether this is a one by D vector。

 so I'm going to call this V transpose， so this is just v transpose sigma minus1。

So the name of it so this is just which is also known as。You know， Aka。Like v dot sma minus1。没有。

Does that make sense？O。And notice that notice that now， I mean， yes。

 V also depends on Sigma because there's a Sigma one transpose in the beginning。

But it depends on a different part of Sigma， right， it depends on the first k entries of Sigma。

 whereas Sigma minus1 is everything but those first k entries。😡，So even if you tell me what V is。

 even if you condition on V。Sigma minus1 is a completely independent vector of random signs。

And now what we're taking is we're taking some fixed vector V。😡。

And taking its dot product with a vector of random signs， we have a taildown for that， right。

 Does anyone remember what it's called。We have something that says。

The probability that what we're trying to say that this thing is not much bigger an epsilon。

 so the probability that V dot sigma minus1。It's bigger than epsilon is at most what if you remember this was like the signs bounded by Gaussians。

Yeah， so well these are plus minus ones right these so the entries of 6 plus minus one yeah so yeah。

 we related this to Gaussians and that was kinch'ens inequality， right？

Wwhichch so that you get as good a tail bound as if they were Gausians。

 so you get something like 2 e to the minus epsilon squared over two times the norm of v squared。

So the key takeaway here is that the taildown that we're going to get is completely dependent on the NorraV。

Okay， so that's the name of the game if we want to understand tail bounds for Sigma transpose B sigma。

It's enough to just bound the normal V。So that's what we're going to do。So let's do that。嗯。

So the norm V。So I don't know if people are， you know， maybe you haven't seen this written this way。

 but you might have known it。So this is this basically comes from the fact that the L2 norm is its own dual norm。

 if you're not familiar with what that meet what dual norms mean。

 let me just write this so the L2 norm， the L2 norm of any vector is equal to the soup。

Over all y of unit norm。Of V transpose y。Right。So the fact that。The fact that you have a， you。

 you're computing the L2 norm and you also here have an L2 norm。

That's that's what's called you know being its dual norm L2 is its own dual， for example。

 if you had L1 norm。So just a little aside， what what is the L1 norm of a vector？

That's equal to like the sum of the entries absolute value right that's equal to the soup over all y of v transpose y。

 but y having norm one for which norm。Actually， it's having Elinfinity normbl， right？

Like if you want to get the L1 norm of a vector V。😡，It's the same as v transpose y。

 where y is a sine vector where for each entry of v that's negative， you make yi negative1。

 for each entry of v that's positive， you make yi plus1。😡。

Then v transpose y will be the sum of the absolute values of the entries of V。

 which is exactly the L1 norm， so L infinity is dual to L1 and likewise the dual of L infinity is also L1 the dual of L2 is L2 right if you have a vector V。

And you take its dot product with a vector y， let's say y has unit norm。😡。

What do you know about dot products， you know that a dot b is equal to the norm of a times the norm of b times cosine theta right that's what we know about。

😡，That's what we know about doc products。So if you're trying to maximize the dot product。

 then I tell you that Y has unit norm。Well， it's going to be the norm of v times the norm of y。

 which is1。Times cosine theta cosine the angle between v and y。

 well if I'm trying to make that angle cosine of the angle as big as possible I should make the angle zero。

 in other words I should make y point exactly in the direction of V。

Right so L2 anyway L2 is its own dual so I can write this the norm of v is equal to the norm the soup over all y unit norm in particular I'm going to make yb pointing in the direction of V of v transpose y。

Okay。And then now again， I can just write down what is why， why is this thing that I boxed and read？

😡，And then I can just write that down together with now why， right？😡，嗯。So this is equal to now。

So let's see， what is that Sigma one transpose， Dsigma 1， Sigma one transpose。D signal one。

And then pi one transpose。Pi -1。诶。Oh， that's D Z 1。 D Z -1。喂。It should have been a Z。

And that's equal to the sum。Overall， j bigger than one of sigma 1 transpose， Dz1 pi 1 transpose。

 pi J， Dz J， Yj。喂。And then now I can just start doing you know， basically the following。

This is at most now the sum J bigger than one。Of。Oh， and first of all， I can I can also swap。

 Let me do one more step。 I can swap basically z's for sigmas again， so this is equal to。

The sum J bigger than1 of Z1 transpose d sigma 1。Pi 1 transpose pi J。DZj， Yj。第个。

And then now I can just repeatedly is the fact that like the norm of A B is like at most the norm of A times the norm of B。

So I can say， look， this is at most the sum of J bigger than one。Of the norm of Z1。

Times the operator norm of D single one。Times the operator normal of pi 1 transpose。Or yeah。

 pi 1 transpose pi J。Times the operator room of DZj。Times the norm of Yj。ok。So。Yeah。😊，Now。

 what can I say？Would I have a diagonal matrix， what's its operator norm。

 it's like the largest eigenvalue right which in this case are the magnitude of largest eigenvalue。

 so it's the largest entry on the diagonal and magnitude。So that already makes certain things easy。

This。This operator norm is just the largest absolute value of any of the signs。

 which obviously is one。This is the largest entry in ZJ， which is the L infinity norm of ZJ。嗯。

What else can I say the norm of Z1 is at most the norm of Z， so this is at most one。

And I think that's basically it and this thing， let me。

 I don't think I got a chance to prove this last time。If I have time， I'll do it today。

 but I promise you that this thing is at most O of epsilon。And essentially why okay。

 so let me try to say in words why that's O upps salon and then you know it's the proof is already in the notes if we have time today for me to actually write down the proof on the board i'll do it otherwise you can take a look at the notes but。

Why is that coming about so remember now。😡，Pi 1 transpose， pi 1 has k non zero columns。

Pi J has canon zero columns。And j is bigger than one， so j is not one。

 so these columns are disjoint right because these columns correspond to basically the first k columns and xk columns and xk columns et cetera。

 so pi1 is the first k columns pi j is the J block of columns。These are a disjoint set of columns。对。

So。Pi remember， is two case sparse， so for any two case sparse vector。It preserves the norm。

Right so again， when you preserve norms， we talked about this already。

 let me be a little loose here when we talked about we already talked about this for the jail lower bound。

If you preserve norms， that implies that you preserve dot products up to additive epsilon， right？

So just look at a vector like take a vector that has all its entries in the first K coordinates。

And then take another vector that has all its non zero entries that has its support in the Jth block of coordinates。

So let's call these vectors A and B A only has non zeros in the first K coordinates。

 B only has non zeros in the J block coordinates what's their dot products？It's zero。

Because they have disjoint support， so A dot B is zero。😡，So pi a dot pi B。

Is probably also close to zero， I mean not probably it is right Pi preserves dot products up to epsilon。

So since A out b is zero。Pi A dot pi B。Is that most roughly epsilon in magnitude？Right， but again。

 the norm of a matrix。M is by definition， the soup over all a B of unit norm。Of a transpose MB。

Like that is the definition of operator norm。Or that's an equivalent definition。So this thing is。

This thing here is basically the soup。Overall， a。Equals b equals 1。You need on vectors of。

Pi a do with well， basically pi 1 a do with pi 1b。Or pi Jb？Which is the same。

Because pi only has non zero columns in the first block， this is the same as。Pi1 a1。Pi J Bj。

And again， AI and BJ have dis support， so their dot product is zero。

Pi preserves doc products up to add epsilon， so this thing must be O of epsilon。

So that's basically the argument。好呀。So in summary， this whole thing is。At most。Oh， Epsilon。

Times the sum over J bigger than1。Of the L infinity norm of Zj。Times the L2 norm of Yj。

Does that make sense？So now we just have to argue from there。对。So let me go to the next slide。

So we said that that thing， so overall what we've said so far。Is。

V L2 norm is at most of epsilon times the sum j bigger than1 of Zj infinity times。Y， J L2。

And then we're going to use a technique that's called shelling。Okay。

 which gets used a lot and compressed sensing so what is shelling so here's the idea。Here's Z。

I divided into these blocks of size K each。They they just do this。Okay。

 let's say that this is the JF block。This is the J minus first block。行。

I'm looking at Zj L infinity norm， that's what I have up here。😡。

That means what's the largest entry in magnitude in the J block well the largest entry in magnitude the J block J block is this entry right here。

😡，What do I know about that entry， I know that that entry is smaller than all the entries in this block。

😡，So in particular， that entry is less than the average entry in the previous block。

So this is at most。嗯。Ofve epsilon times the sum of J bigger than one。呃。Z J minus1 L1 norm。

Divided by k， that that's the average magnitude of an entry in the previous block。😡，Times Y JL2 norm。

And then now I can do kshi Schwartz to compare L1 and L2 norms right Zj minus1 is a K sparse vector so this by the way。

 this is called shelling this business of comparing a norm in one block to some norm in the previous block。

有人。嗯。And by Kohi Schwartz， this is at most。呃。O of epsilon times the sum of j bigger than1 of Zj minus1 L2 norm times root k。

So the L1 norm is at most the L2 norm times square root of the sparsity that's by Koshhi Schwartz。

Divided by k times Yj L2 norm。I can pull the you know。

 basically the root and K cancel and get a root the denominator。

 so this is equal to O of epsilon over root K。Some J bigger than one。Of Zj minus1 L2 norm。

And this is Koshhi Schwartz。Swartz does not have a T despite many people making that typo。诶。

Times Yj L to norm。And then now I can do koshi shorts again。This is at most O of Epsilon over roquet。

Times。The sum J bigger than one of Zj minus1 L2 norm squared square root。

Times the sum J bigger than one。F Yj。E norm squared square root。And of course， now。This is。I mean。

 this is just at most the norm of Z。Basically what we're saying is okay。

 so what's the squared norm of Z， the squared norm of Z is。Block by block。

 take the squareum of the block and add them together。Right， that's the squared R Z。So this， I mean。

 this thing in the sum is the squared neuro Z。Except if you're missing the last block but whatever it's so it's at most the square numbers of you you took a square root。

And similarly， this thing here is at most the norm of why。This is one， this is one。

 So this whole thing。Is。At most， oh， Epsilon of a roque。

So that's exactly what we wanted we wanted to show that。The norm of V。At the top left is small。

The normal V is bounded by something， and we got are something。

So now this implies by Kin's inequality。Where's K？This is my kin right here。Ps。My kitchen right here。

 so what we've shown is now this is at most。So the Lt2 norm is at most epsilon over root k。

 so the Lt2 norm squared is epsilon squared over k。So this is at most two E to the minus。

Epsilon squared。Over。Two epsilon squared over K。Right， which is like two to the minus omega k。

Which I can make be， you know， I can make this be at most delta over three remember k is like some constant log whatever delta so as long as I make the constant C big enough。

This that most dealt over three？确认。So good， so a trans sigma transpose a sigma is what we want with probability one。

Sigma transpose B sigma。Is what we want with failure probability at most Delta over three。

Then B transpose sigma again we're going to say failure probability delta over three sigma transpose C sigma is also going to be failure probability delta over three so by union bound the probability that anything doesn't look like what we want is that most zero plus delta over three plus delta over3 plus delta over three which is delta so the probability that we fail to get a norm that we like is at most delta Okay so that's b sigma transpose b sigma。

嗯。Sigma transpose B transpose Sigma。Is of course， the same thing as sigma transpose。

 I mean sigma transpose be transpose Sigma is a number。It's a real number。

 so it's the same thing as the transpose of itself because the number is of course it the one by one matrix。

 so this is the same thing as sigma transpose B sigma transpose。But that's just a number。

 so that's Sigma transpose B sigma。Okay， so if Sigma。

 we already said that Sigma transfer B Sigma is likely to be small。Nothing new here。So in fact。

 we don't even really need this to be delta over three if we haven it be Dlta over two。

That's enough because the action。You need to prove something for B Sigchas as B Sigma。

 then you get it automatically for B transpose Sigma。

And then you need to prove a bound on Sigma transpose C sigma。

 so let's do sigma transpose C sigma now。So Sma transpose C Sigma。I's going to look very similar。

This is not C sub Sigma。 that's C sigma。So this is。

The sum over all I J bigger than one where I is not equal to J。Because when I equals J， that's a。

 that's not C。Sigma Sigma I transpose。DZ I。Pi I transpose pi J。D Z J。Sigma J。I think that's right。

And then right off the bed， I'm just going to say， look， you know， that's at most。嗯。So in fact。

 if you look at the absolute the magnitude of this thing， even that's equal the magnitude of that。

 even the magnitude is at most the sum of all Ij bigger than one I not equal to J。Of。

Now I'm going to say look。嗯。嗯。Oh， actually。Okay， so before I do that， let me say the following。

 which is。嗯。Sorry， let me just actually see the following。So that is true。

But I guess one thing I want to point out so actually let me write let me write。

 let me just write something else and then I'll go back to that， sorry for the confusion。

But the point is， look， this is exactly a quadratic form。So I can directly use。

 I'm going to use Hannsson right。So that applies that the probability that over sigma。

 that sigma transpose C sigma is like bigger than epsilon is at most。

 so constant times e to the minus epsilon squared over the Frbeius norm squared of F。Plus。

 e to the minus some constant some constant epsilon over the operating room of C。Does't make sense。

 so this is Hansen Wright， which we've seen before when we analyze jail。So that means that。

We now want to bound the Frbes and operator norms。If we've bound those。

Then we can just plug that bound into Hanson right and get something。

And that's going to be exactly what we do。So let's first look at the for ayn squared。

So that's equal to， again， like remember what C is， so what does C look like？

It's the funniest looking at all of them， I guess。So there's the diagonal blocks。

And then there's this， and there's that。So this， the diagonal stuff is all zero because that's a。

This is also zero because that's B and this is B transpoposedse so C is just the stuff that's kind of left over。

So that's all see。Okay， so you know， I'm just going to basically break up this region into like little blocks。

K by K blocks。And then sum up over all those blocks。 So this thing is equal to。

The sum over blocks Ij， where I is not equal to J and IJ are both bigger than one。

Of the Frbeia storm squared to that block， remember Frbeia storm squared means。

Just sum up the squared entries of the matrix。So this is now。The familiaror squared of DZI。

Pi eye transpose。Pi J， D Z J。谁？And then now I'm going to say that。

This is so people might not be so familiar with this。

 but let me write it down if you look at the Frbei form of AB。

I claim is at most the operator room of A。Times the Frbenius number of B。Now， why is that？So B。

 so A is this matrix here。And then B， I can just write B column by column。😡，So there's column one。

There's column two。It's column three。E cea。So that means that。A B forbenous norm squared。

It's just the sum of all J。Of the norm squared of ABJ。系。But again。

 what's the definition of operator norm， the operator norm is like what's the worst case that can blow up the norm of a vector by when you apply this matrix？

😡，So a times BJ， its norm is at most an operator norm of a factor larger than the norm of BJ。

 that's the definition of operator norm or L2 to L2 operator norm。😡，So this is at most。

The sum over j of the operator norm of a squared times the norm squared of bj。

And then I can pull this thing out。And what I'm left with inside the sum is just the forbeous norm squared of B。

 so this is equal to now the operator norm squared of a。Times the Frbeian norm squared of B。

And of course， now。That was equal to the Frbena storm squared。So if I remove that squared。

That means I put a square root here， I put a square root here， that means I remove these squares。

So I've shown exactly what I want。Where is that A B for beingius norm is that most operator norm of a times for beingnius norm of B。

Does that make sense？Okay， so。Let's now use that。I only put the chat in case you type anything so now I can say look and of course now this also means that like if I have aBc or it'll say。

ABC forious norm。Well， that's by this reasoning， that's at most the operator room of AB。😡。

Times the Frbii norm of C， which itself is at most the operator of a times the operator room of B times the Frbini norm of C。

So that's what I'm going to do here， I'm going to say， look。

This is at most the sum over all I not equal to J ij bigger than1。Of the operator norm。Of DZ I。

 and there's a squared here。So squared。Times the operator room of pi I transpose pi J。

Squared times the Frbenius norm squared。Of D ZJ。ok。And again， we've already seen this reasoning。

 so these are dis blocks because I is not equal to J， so this is O of epsilon。

That's what we said before。The operator norm of ZI is just the Lfinity like DziI is a diagonal matrix with the ZI on the diagonal。

So the operating norm is just the largest entry of ZI so that's L infinity norm。

 so this is the L infinity norm of ZI。Squared。And this is you set up the squared entries in the matrix。

 but again it's a diagonal matrix， so this is just again going to be ZJ。L2 norms weird。So altogether。

 what this looks like is。It's at most。Oh， of Epsilon squared。

Times the sum I not equal to J ij bigger than1。Of Z Elenfinity norm squared。Time ZJ。Ll2 arm squared。

可以。😊，And of course now you're an expert in shelling， you've seen shelling already once。

 so we're going to do the exact same thing again。So let's go to the next slide， so we said that。

So basically what we said is that the forbeous norm of C squared is at most。

O of epsilon squared times the sum over i J greater than1 I not equal to j of。

Z J infinity squared times or Z I， sorry。my pen is obviously dying on me Z J。How soon I'm squared。

We already saw you can bound the L infinity norm。By whatever root k times the L tu norm of the previous block。

😡，OkayBut then now you this is squared， so this is at most。

O of epsilon squared over k times the sum over all Ij bigger than1 I not equal to J。Of Z I minus1。

 the previous block， so this is shelling。Loon norm squared times Zj Ls2 norm squared。This is showing。

And notice that all the terms in this expansion appear in the expansion of。Some over I of Z。

Ltoon arm squared squared。Right。If you expand out， if you expand this out。

 what you get right what you get here is some of IJ。Of Z I。Time C j。So this。

Contains all the terms in our box thing plus more， right because our box thing doesn't contain the diagonal。

 it doesn't contain the case that Ij equals one。😡，But this does， and of course。

 this is just the same thing as Z L2 norm squared squared。Which is one squared， which is one。

So altogether， this thing is at most o of epsilon squared over k。So we've shown that。Overall。

 we've shown that C for Venus room squared。Is at most O of epsilon squared over K？对。

And then the next thing you have one has to show is the operator norm。

So let me not you know I think you're getting bored with all these similar looking calculations。

 so I'll just write what you do you just say look see operator norm。This is a symmetric。

 this is a real symmetric matrix， so it's equal to the soup over all y of unit norm。Of Y transpose C。

Which again is equal to the absolute value， some I not equal to J Ij bigger than1 of Y I， DZ I。

Pi I transpose。Pi J， D Z， J。坏者。系。And then you know， you basically do some shelling。

 you do a koshi shorts， and this is basically bounded by O Epsilona verque。

Okay i'm not going to do it out because honestly compared to what you've seen it's the same kind of things all over again there's nothing really new here if you really want to see this you can see it in the notes i've already uploaded this to the website these notes so。

ind of altogether， what we have is that the Frbenius norm is bounded and the operator norm is bounded by O of epsilon over k。

And then now you just plug it to dancing right。And you know， you're done if you do that。

 so let me not even bother doing that because there's nothing really interesting there。Okay。😊。

So that's basically how this proof goes I don't want to spend time writing out all the math for the last parts because we do have only 35 minutes left and I do want to start on the next topic which is sketching for linear algebra。

So before I start on the new topic， any questions about anything you saw in the KW analysis？

RightAgain， that the reason that we set k the way we do is because。Basically， of here。

We said that your RIP， where you preserve k sparse vectors and K is like log， whatever delta。

And that's because of right here when we're analyzing sigma transpose b sigma。

 we got a two to the minus omega K， we wanted that to be at most delta or delta over 2。

 so that made k be roughly log whenever delta。And if you do the same thing for Hanson W with Sigma transpose C Sigma。

You know， you basically you're going to end up with something again that looks like2 to the minus omega k。

 so that's also going to require you to pick k to be some constant times log whatever delta。Okay。嗯。

Speed us up。So any questions it seems。No。Okay， so the rest of today。We're going to do sketching。

And not just today， but also like。Wednesday and probably also a little bit into next week as well。

 sketching for linear algebra problems。And we're going to look at things like。

Approximate matrix multiplication。A professor actually had a question about so it seems like you can use any RIP matrix you want Yes in the first part so that's true y。

So it seems you can use a non random one。Yeah， it's right， it doesn't have to be random。

Okay so is well what is a non random one then that's that's a very good question and that's actually a very big open problem so we don't know we don't know anything so and probably this the next piece that will' have a homework related to this but。

If you want a matrix to satisfy this RP， we know random constructions that give you roughly K rows K log D rows。

 okay， but if you want a deterministic。Kind of construction of such a matrix。Then。Essentially。

 the best we know is roughly K squared rows instead of K rows。

There was a paper in stock 2011 by a bunch of math people， so like Jean Bourgain， Sergei Kodigan。

 other people who areop what's going on？Others who are masters of analytic number theory。

And they managed to show using tools from analytic number theory。A deterministic construction。

Specifically when K is roughly root D， a little bit less than root D。😡。

They can show how to come up with a KRIP matrix。😡，Where the number of rows is just a little bit better than k squared。

 it's like k to the 1。99999。So that that's the only。

 I said of the only paper that's out there that manages to get anything better than the K squared construction。

Okay， so so what do people do in practice， they randomize practice， yeah， bigger random matrix。I see。

诶。If we choose randomly， is it just usually I。 So I say it again。

If you just choose like totally randomly， usually RIP Yeah we'll we'll see that we'll see more of this later when we talk about compress sensing。

 but yes， if you pick like basically any jail distribution。

 so what you can do is you can take a net of the set of all case prospects as long as your your matrix satisfies the jail condition on that net。

You can extend it to the set of all infinitely many case bar vectors。So the net has sized roughly。

Roughly， you know。Let's say two to the K times n choose k JL says you need log n over Epson squared rows。

 so if you take the log of that it's roughly k times log of d over k。When I said。

 and I'm meant to sayD， so they D choose K choices of where the non zeros are。

For each one you take a net of size you know o of1 to the k so the log of that altogether is roughly k times log d over K so if you make a random matrix with Gaussian entries or a fast jail matrix。

Or whatever， yes， you will get。You will get R I P with high probability。

What was the definition of IP。You preserve the norms of all case bar factors。Yeah。

 so it's parameterized by K as well as epsilon。Okay， so back to sketching for linear algebra。

 so you can use sketching to get faster approximate algorithms for things like a matrix multiplication。

 least squares regression。And other forms of， you know， and other。Plus。

 other constrained regression problems。As well as low rank approximation。

 approximate low rank approximation。Ca means's clustering。

which you might not think of as a linear algebra problem， but as you're going to see later。

 it turns out that it can be Ca' clustering is actually a special case of constrained low rank approximation。

 it turns out。And you know， there are a bunch of applications and there' a there's actually a book called Sketching。

As a tool。For numerical linear algebra。This is by David Woodruff。Theres a book so it's free online。

 I think it's free so you can if you're really curious， you can go and take a look at that。

 but we are going to recover many results in the space in the course。Okay。So let's get onto it。

The first thing Ata talked about is approximate linear algebra， I mean。

 approximate matrix multiplication。So。😊，Approximate matrix multiplication。So the idea here is。

We have a matrix a。Then we have a matrix B。A has N columns， B has N rows。

And let's say A also has D rows and B has P columns。And we want to compute a transpose B。

And you know， using four loops and we just want to be fast， so using four loops。

This would be something like oh of。NDP phps。没。And。The question is， can we do faster？And you know。

 people in theoretical computer science have studied this。If the matrices are all square。

Then there are you know there are fast matrix multiplication algorithms going back to Strawin right so let's see so log7 over log two is roughly we it's roughly 2。

8075 so you know。We had Strawin。Sa that so basically you can get time up to log factors O of like n to the mega Strawson said that the exponents omega is less than what。

Or it was less than。2。80735。That was the first thing that it was the first paper that I got anything better than N cubed。

And then there was， there was a bunch of stuff after that。

 which there was a long history and it not go through all of it。

 but then we had Coppersmith and Winnirad。In the 80s。

That actually showed that you can get omega down to something like 2。376。It's less than that。

And then again， there was for there was absolutely nothing for a while。And around the same time。

 there were two independent works， one by Stas and one by Vasilovvsco Williams。This was 2010。

 and I can't remember exactly， but this is the 2010s。嗯。So Staler said 2。374。

 but it was based on Comworth Winrad。And then Vaselovska William said 2。37。You know， two， eight， six。

 four， two。And then she was one up。Just a couple years down the road by Laal。

Who came up with two point？3，7，2。8ight， six， three，9。And then most recently this year。

 Vasloska Williams came back with。Her former student Josh Almond。b w。This is 2020。And， you know。

 they yet something that is。Yes， again， shaves off something。Actually。

 oh I wrote it down and then I figured out where I put it。But， you know， it's like。

I think it's something like 2。37 maybe27 or something like that again it's it's you know quite similar to the previous but a little bit smaller。

But as you may or may not know， these basically from what I've heard is that none of these algorithms are practical whatsoever。

 except for maybe Strau and if n is big enough。All the rest are just for purely theory interest。

And also none of them are n squared either， so n squared would be the best possible because the output itself has size n squared。

Just writing it down takes that much time and of course reading the input takes some square time。

If you don't have a square matrix， two square matrices， but you have rectangular matrices。

 people do study you how fast you can do rectangular matrices as its own thing。

Or you can also reduce to the square case because you can say， look。

If I have two rectangular matrices， I can just divide these things into squares。As such。Right。

 and then I could do a bunch of so if I just break this up as like M1 M2 and M3。And this is like A1。

 A2， A3。And a4， I can say that MA is equal to。This。Oh actually。

 there should be an equal number of them。So。Let's pretend that there were an equal number of them。

So this is equal to the you know I goes from one to three of MI AI right so I can you know there is a way to you can reduce if I if I have a square solve or have a square multiplier or I can use it。

To do rectangular multiplication too， although sometimes you can do better than this reduction if for rectangular matrix multi。

 but in any case all of this is not that fast， especially not in practice so is there anything we can do to do better and those theoretical bounds like specific logarithms like the Strsa are they like more obscured。

All of them end up essentially all of them。Basically say， you know。

 I can do some kind of recursion where I do less rest recursive multiplications than the naive way。

Like stressing， but I think that， you know， they developed their own language now to find these kinds of identities。

And now the name of the game is like， how can you find such identities and？嗯。

I'm not I'm actually beyond drawaw and， I'm not even sure exactly how they work personally。

But I think if you look at， I think， for example， Vsloska Williams has taught courses before on。

All these methods for fast matrix multi， so she should have。

 I imagine some good course notes on that。O。So。😊，Kind of the first paper that managed to。

Have this idea like how can I speed up approximate matrix multiplication， so it was by。Dnaez。

 Canan and Mahoni。And this is back in 06。The idea is we won't。Compute。A transpose B exactly。

But rather。Some matrix C。Such that。A transpose B is close to C， or C is close to a transpose B。

Let me call it some Xr。Okay， does that make sense？So you know。

I'm going to speed up the computation of the matrix multiplication。By doing some sketching。

 but you know I'm not going to get the exact answer for a transpose B。

 I'm just going to get some other product matrix C which is close。And they looked specifically。

 so DKM。Did this。For specifically forbeous norm。So what they said was that。A transpose B。Mus C。

Fbeus norm is going to be at most epsilon times the Frbenus norm of A。Times the would be。

So that was their approach。And how did they do it？Vs sampling。Okay。So if you write， again。

 this is a nice fact about linear algebra， you can verify it offline if you wish， take your matrix A。

ok。😊，It has， I said n columns right， so it looks something like or。It has N rows， actually。

 it should have， let me go back a little bit。This is really a transpose。

I'm trying to multiply a transpose times B， so the number of columns of the first matrix has to match the number of rows of the second matrix。

So A and B both have N rows。Which means a transpose has n columns， which matches the N rows of B。

 so these are conforming matrices to multiply。嗯。So let's go back now to DKM。So A has N rows。

Let's call these in rows A1 up to anN。Transpose， maybe。And B is equal to， again。

 a matrix that looks something like B1。Up to B end。And just a fact about matrix multiplication。

A transpose B is equal to the sum i goes from one to n。Of AI， B transpose。So this is an identity。

 this is just this is something that's true about matrix multiplication in general。😡。

You can always write the product of two matrices as a sum of outer products of the rows of the matrices。

Okay， well here I transpose the a normally would be like you take the sum outer products of the columns of the first matrix with the rows of the second matrix。

ok。If I didn't do the transferpo on a。So this is a very useful fact to keep in mind it's if it's something that's not already on the。

Front of your linear algebra fingertips。So this suggests a sampling approach。ok。So， d canM。

The way Dcam works is it does non uniform。Non uniform sampling。嗯。For each。I between one and。We keep。

The I。We keep the IF outer product in that sum。With some probability PI。诶。

Or if you are you know another thing that also works is。诶。Or。s播。Some ans。From。Some of our AI。

 BI transpose IID。We're each。Sample some and。Equals。AI BI transfers with probability PI。Okay。

 so what I mean by this is。We're going to pick one we're going to pick a random we're going to pick a random I between one and n that gives us AI and B we're going to get AI B transpose we're going to pick another random J between I and1 then we're going to take AJ bj transpose and then we're going to sum them up all up together so our C at the end of the day is going to equal we're going to set our C to be basically one over m times the sum。

I equals， let's say。That's right like this。R goes from1 to M。Of。AI。Let's say AIR， V IR transpose。

Over。诶。P I。O。And the reason you divide by PIR is to get an unbiased estimator。Because。

 what's the expectation of C？By linear expectation， it's equal to this expectation。

But these are all II right where you're just kind of sampling I outer products from the sum。

 so this is just equal to。The expectation of a single one， which is AI， BI transpose over PI。

Because we have whatever M times M。Times the expectation is the first one because all M of them have the same expectation。

And this is equal to like。The sub over all I from one to n。Of the probability that。We sample I。Times。

AI， BI transpose over PI。And the problem that we sample I is PI， right？So these things cancel。

So this is equal to the sum of AI B transpose， which is just equal to a transpose B。对。I mean。

 another way， you know， I said。AndAnother you could also do， which also works。Is to do the following。

 just keep the I out of product with probably API。So then you could say， look。Another thing you do。

 So or you could do C is equal to。The P sum i goes from 1 to eta to n， let's say。Eta I times。AI。

 B transpose over Pi where Eda。Is equal to one。If we kept。

If we kept the I sum man and zero otherwise。And the problem that we keep the I sub is again going to be PI。

So again， this also gives an unbiasedestimator， the expectation of C is equal to the sum I goes from one to n of the expectation of A to I times AI。

 B transpose over P。But the expectation of A to I is PI it's an indicator random variable that's one with probability PI so this cancels that so this is also this would also be an unbiased estimator so either either of these would work and they would give you an unbiased estimator。

Okay， so that does that make sense， do people have questions？So this。

 this Ps are like non uniform or some。That's right， they're not uniform they what' determined。

So what are the PIs， maybe's your question like how should I pick the PIs？And DKM。

 does that make sense that that's what we need to understand now。Yeah， yeah。I mean。

 so this would be an unbiased estimator for anyPI。😡，But we don't just want an unbiased estimator。

 we want small variance， right， We want to say that our estimate is actually close with good probability。

So for that， it's not enough to just say that we have。We have the expectation correct。

 We need to say something about the variance。Okay， so how are we going to do that？嗯。

We're going to say， look， the probability that a transpose B minus C for beingo norm squared is bigger than epsilon times a for beingnous norm times B for beingous storm。

Well， this is just by Markov's inequality。And sorry， this should not be weird。

Or by the second moment method， you know， basically square both sides。And then new Markov。

So you can square both sides of Du Markov this at most。The expectation。Over。

A transpose B minus C for beous norm squared。Over。Epsilon squared。AF squared， B F squared。Right。

 so what we will show we want。That。We want that basically the expectation。

Of a transpose B minus C for being syndrome squared say at most。Up to some constant。

Is that most something like？A squared。Times b squared。Over M。喂。If we could show this。

 then that would imply。That would imply that。And being at least something like one over epsilon squared Delta。

Delta， sorry， or actually， let's say let's say Eda suffices。For failure probability。Atmo data。Right。

Just by using just by plugging it into here。Okay。And indeed。

 you can get that if you set the PIs appropriately。

 and it turns out that the optimal setting of the PIs， which was in DKM。

Is to basically set PiI to be proportional to the product of the row norms。

 so you set PiI to be equal to。嗯。The norm of AI。Times the norm of B。

So this is the AI is the I throw of A， B is the I throw of B。😡。

And you normalize it to make sure that the probability is sum to one。Does that make sense？

The definition。And。If you do this， you can prove that indeed。This does hold。对。

So if you set PI as this and then you do the above。

 you'll get the bounded second moment that you want。

 you can plug it into the Markov above and you're happy。

I'm not going to do the calculation on the board because I only have 13 minutes left and there's more that I want to tell you I think this is kind of a less interesting calculation so i'll just put this in the notes and you can read you can read the calculation of the notes if you really want to。

What I will say though， is there's already something that's kind of interesting here。

 which is what if I don't want failure probability Eta。

 but what if I don't want failure probability a third？

But I want failure probability very low like Delta where deelta is super small our usual trick was。

Then you do this a bunch of times in parallel and then you take the median。😡。

Right kind of the median so once you have anestimator that works with probability a third or fails fails with probability at most a third。

 if you take the median of log whenever delta copies of that。

The median will work with probably one might is stealelta by the turn off bound。Of course， you know。

 we could just set a to to be deelta year the problem is that。😡。

M is then going to depend on one over delta， whereas I would I really would prefer that it depends on log whenever delta right I don't want to have complexity that's polynomially in whenever over delta。

 I prefer log whenever deta that's better。Um， but what's the problem here with like repeating many times and outputting the median？

What it's a matrix。 Yeah， it's not a number。 It's a matrix。 So what does the median even mean， right。

 You run it each time， each time gives you a different matrix。So what do you do？所。If you think of。

 you know， numbers， matrices， whatever， think of them as just。😡，Objects living in a metric space。

Okay so numbers the metric there is just the absolute value of the difference。

 so i'm saying one number is close to a number one number is close to another number。

If the absolute value of the difference is small， okay。

 and there we said basically we're we're we're going to out put the median if you have an object in a metric space。

You know， now what kind of what do I want the medium to be to make the argument work well？

So heres of the here's kind of the idea。The idea is if you really look at this kind of median of means analysis。

 what it says is， okay， if I set Ada to be like 90%， let's say A nine Ada sorry， A is 110。

So one tenth of them fail in expectation。I repeat log whatever Dlta times。😡，Okay。

 so let's say I repeat。So like boosting。Let's a boosting success probability。I'm going to repeat。

T times。Which is theta log whatever deelta。What do I know by turn off？

I know that kind of two thirds of these repetitions are good。

 two thirds of these give me a matrix that actually has bounded error。

 the kind of error bound that I want。😡，Okay。So again， forget that it's a matrix。

 just think that it's a point in a metric space where the metric is forbenius norm。😡。

So my picture is I have a bunch of matrices that I'm getting output。Which are good。

 two third of them are good。And then I do have some that are bad， maybe at most the third are bad。

 So the bad ones are kind of like far off who knows where they are。

 but they're kind of not near the they're not near the truth the truth。

the true matrix A transpose B is like somewhere here， right？

And two third of my matrices are close to it。And maybe one third is far away。

So the observation here is， look。I don't know that yellow point。

But what I do know is I know all these block points。😡，And what do I know。

 I know that by triangle inequality。If I look at this kind of central cluster。

Every one of those black points is close to the yellow point。

Which means that they're close to each other by triangle inequality， right because the distance。😡。

You know， the distance from。Here to hear。Is at most going to the yellow point and then going back to this point？

And since each of those legs is small， that must mean that this is small。有。So what that means is。

At least。Let's say at least two t over three of the points。Are close。超。

At least two T over three of the points。You see， the black points are all close to the black points。

So the name of the game now is just basically find any black point。😡。

That's close to most of the black points。So this I can do via just t squared comparisons because I know all the black points。

 right？I don't a priori know which ones are in the red box。😡。

So I just need to find anything that's in that red box。😡。

So I'll just loop through all the black points， sorry， I'll loop through all the black points。

And all just compare them with each other。😡，And the first one I find that's close to the majority of black points。

 I'll just return that as my quote unquote median。😡，Does that make sense？

It's a definition of a close。Close close basically， you know。

 I know that their distance to the yellow point is at most this， right？

The good points have distanced the yellow point that's at most this。So by triangle inequality。

 their distance to each other must be at most twice that。😡。

So if I find a point that's at most two epsilon Af Bf from all the other points。😡。

That from half the other points， I'll just say this is a good point and I'll put that。

 I'll put that as my matrix。And that's my proxy for median。Does that make sense？Yeah。

 instead of like stopping。When you。I think the first time you see that， could you like it？

Go through each one If it is in median distance to all the other points。

 then we turn the one to like the lowest median。That's probably similar， I guess。诶。Yeah。

 so actually I think you actually， I think lose something that depends on the dimension of the matrix if you do that。

Oh wait， so wait sorry say what you said one more time Oh I said like for for each point and matrix take the。

😊，The distances to all the other ones and like you know。

 find find the median or just like like entry wise in the matrix so for each entry the matrix。

just like guess those are the tee points， you have like each of the tee points find it's like。

 you know。The the norm of the the forennious norm of the difference between that and all the other matrices。

 Yeah so that's exactly what I'm proposing。And then you return the first one you find that's close to like more than half of them。

 but notice that。This running time is now like t squared you know。

 it takes a certain amount of time to compute distances between matrices。😡，But it's。

 you know you're doing t squared of those， you're doing t squared matrix distance computations。

 whereas normally for the median of numbers you're only doing it's a linear time thing。

 it only takes OFT time to find the median of t numbers， right？😡，So。😊。

That was actually an open problem and the last time I taught a sketching course。

Before I moved to Berkeley three years ago。That was actually an open question。

 which I posed to the class。And one of the students kind of for， you know， as part of the course。

Actually， he did something else for the final project。

 but he did this on the side as a secondary final project because he felt like it。

 but that's not required by the way， but anyway， he proved he managed to show kind of a general algorithm that said。

If you have any kind of scenario like this in any normed space， it doesn't have to be forbious norm。

 it doesn't matter whether matrices numbers， whatever。😡。

If you have a situation where you have tee points in a norm space。

And you know that there is a cluster that's larger than half the points。

 there is a cluster of like two thirds of the points that are close to each other。😡。

There is a deterministic O of T time algorithm to find a point in the cluster。😡，And actually。

 it's interesting his algorithm。Is a kind of you can view it as a generalization of the deterministic heavy hitters algorithm that you did on PSet one。

 problem three and PSet one。Where you said like， you know。

 there's a deterministic algorithm for L1 heavy hitters and insertion only streams that uses only 2K memory。

U。😊，His algorithm is somehow very inspired by that。By that algorithms operation so anyway， fun fact。

 of course， if you don't want to be deterministic if you're willing to be randomized another thing you could do is just like pick a random point。

A random point is probably in that red box because most points are in that red box。😡。

So pick a random point and then just compare it to all the other points and check whether or not it's close to the majority。

 if not， pick another random point and just keep doing that until you find one that's actually close to everyone。

So in expectation， you'll only need to test a constant number of random points。

Each one only takes T time to check distance to everyone else。

 so in expectation this is only taking OFT distance comparisons， distance computations。

Questions about that。How does this boost our？Probability of success or it allows us to boost it to Delta。

Yeah， so what you'll use the turn off bound to say is the turn off bound will imply this picture。

 the turn off bound will say。😡，That there is a red box around the true yellow point that contains two thirds of the points。

😡，Right。And then now that you know that fact， the name of the game is just find any point in that red box。

😡，嗯，OK。I see that sense is just telling you that the red box exists。

That's going to happen with probability 1 minus delta。😡，Now find a point in the red box。Okay。

 that's clear。对。Okay good so I think that's all I want to say about the sampling approach here for matrix multiplication let me say there's another approach so。

So DKM。You came into sampling。Charlos in '06 same year but after。给 kind of a。You know， JL approach。

Where he picked a matrix pi for him， he just picked like a random sign matrix or something。

 actually he picked the fast scale matrix so pi。Pi is like a JL matrix， so it maps down to MRRs。

Actually， this should be end now。And what he said is he's just going to set C to B。

Pi a transpose pi B。And then you want again to show that。Kind of a transpose B， so the probability。

Over pi pis is a gel matrix that a transpose B minus pi a transpose。Pi B forbeino norm。

 probably that's very in epsilon times of fbeino norm of a times the phbeino norm B。

Should be at most Delta？And what he showed is that。If P satisfies jail。

 then you can kind of get this for free from the jail property。And。Out of。We're running low on time。

 so I'll finish this on Wednesday， but the main idea is kind of if you look at。

If you look at kind of a transpose B。As a matrix， know what does this look like？

It basically looks like， you know， each entry is like， you know， a one dotted with B1。

A2 dotted with B2。It looks like a bunch of dot products。Right。😊。

Whereas kind of sorry for my phone in the background， if you look at pi a transpose。 pi B。

That looks like also a matrix of dot products， but it's like pi a1 dotted with pi B1， etc ceter。

 So if you look at the Frbenius norm squared of the difference，Pi a transpose。

Pi B minus a transpose B。That looks like a matrix where like each entry is kind of pi a with pi AI do with pi Bj minus AI dot with Bj。

And then if you take the Frveni storm squared。This is basically now。

The sum of her Ij of like this thing squared。Right， does that make sense？

And what do we know about jailL？Since it preserves norms of vectors， it also preserves dot products。

Basically， Pi preserves this dot product。So kind of if you're summing up a bunch of small things squared so you get a small thing。

 that's roughly why it works， Does that make sense。

So we're going to see that more formally next time and let me stop recording。



![](img/21349bf6154bf1852ff7c73541898ba9_2.png)