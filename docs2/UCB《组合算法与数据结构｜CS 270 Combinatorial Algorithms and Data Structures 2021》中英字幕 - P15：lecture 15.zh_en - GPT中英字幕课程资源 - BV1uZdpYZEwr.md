# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P15：lecture 15.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/10fe05bb1beb4869e3a8daa8954ff4d9_0.png)

![](img/10fe05bb1beb4869e3a8daa8954ff4d9_1.png)

嗯。嗯。

![](img/10fe05bb1beb4869e3a8daa8954ff4d9_3.png)

![](img/10fe05bb1beb4869e3a8daa8954ff4d9_4.png)

Welcome everyone， good to see you all today we'll continue talking about spectrograph theory。

But before I get to it， I guess just wanted to make a。

Quick announcement so we posted the details on the project course project the course project will be a project with in groups of two or three people and you suggest a bunch of reading projects online you're also welcome to pick your own reading project or if you'd like to do an implementation project you know just pick your own and let us know and I guess the first deadline which is sort of for the project is tentatively April 1s which is in about two weeks you would be required to just submit the names of your team members and what topic you're going to pick and。

Probably in a list of what what resources， what papers you'll read。

 this is just took for us to suggest changes early on and。Yeah。And these。呃。Yes， so so。I guess。

 you know。For a reading project， the kind of thing I'm thinking about is you pick one of the topics which are listed there or one of your own and you read a paper or two and you distill the at least one technical。

嗯。Proof or proof of an algorithm or it may not be an entire proof。

 but it could be a proof sketch of a very long proof。

 but just something that you distill it to the extent that it's sort of at the level at which we lecture in a class as in you understand it at that level that'll be a sort of a good good goal sort of to pick something and really understand it really well。

嗯。And yeah， I hope you have fun reading something interesting Okay so that was that's one deadline coming up the other thing which I wanted to mention is the course has a exam like as in it's a homework with no collaboration it's definitely be shorter and for a week as it was post it will be in the week of April 1s to April8。

嗯。And。This would be the exam。And then finally you know we have I guess one homework is due this Thursday。

 I'm going to post another homework on Thursday so that'll be homework five。

 itll be due I guess just before the exam on April 1s and then after that after the exam you'd have yet just one more homework on April 8 which would be homework 6 and after that would be left with just two weeks in the class and you'd use those two weeks for the course project so that's sort of the plan for the rest of the class。

In terms of logistics。 Alright， so let's get back to。An exploration of。Specttrograph theory。

All right， just to remind you where we were quickly。 So what happened was we。

Looked at the lapla of a graph。 the lappl of a graph is。D times identity minus the decency matrix。食啊。

So that's the matrix and then we looked at it's a PSD matrix， it's the quadratic form。

Given by this X is xj whole squared or all Ij edges and then the quadratic form is as if you're minimizing the length of the edges some square length of edges and physically we thought about it as a network of springs and then。

This is trying to minimize the total energy of the system subject to whatever constraint you put on it。

And then we saw that this just eigenvalues of these lapplian matrices actually reveal structural properties of the graph。

 for example we saw an easy theorem which say that if G has k connected components。

 then lambda k is zero， I guess if lambda k is zero。

 note that lambda1 to lambda k also zero because we all the eigenvalues are non negative。这点。

Non negative and we've sorted them in increasing order so if there's one connected component you'll see 10 here in the sequence and if you're two you'll see two zeros and then K connected component you'll see k zeros in this list of eigenvalue。

Okay， so so that's sort of an exact theorem， and then we looked at a robust version of that。

And that was this Chegers inequality and Ches inequality essentially says that。If your eigenvalue is。

The second economic is small。If it's second againvalue is zero。

 you know that there are two disjoint components。But if the second angle is actually small， not zero。

 even then there are two components that are very sparsely connected to each other and in fact。

 formally we quantify this as with expansion。So basically， we proved that。

If the if you look at the expansion of the graph， which is minimum of。

Expansion of all sets of size at most n over2， where the expansion of S set is the number of edges between S and v minus S divided by the volume of s。

 So this is the probability that if you start at a random point in the graph on in the set S and you take a random step。

 the probability that you leave the set that is the expansion of the set。And then， you know。

 we have this chis inequality that tells us that the second eigenvalue is。

Quite closely linked to the expansion of the graph。And。In particular。

 I guess there are two directions。Let me write what the directions mean so if。

Second eigenvalue is large。嗯。Is at least。Let's say some constant C。

Some constant C like think of this constant as 0。1， let's say if the second eigenvalue is at least 0。

1， then the expansion， then the graph。Has expansion at least the constant。Okay。

 that's what you conclude from here。Maybe005， but it's some constant so if you're。

The second one is a constant and you have at least a constant expenditure。

So this is a way in which you can check that your graph has a large expansion。

And then the other direction is， if the second eigenvalue is small。

I guess yeah if the second egg value is small。Less than epsilon， then there exists some cut。

There exists some cut s comma v minus S。Such that the expansion of the set S is at most square root of two epsilon。

Okay， it's。And。Not only that there exists such a cut。

 we saw a randomized algorithm to produce this cut。

There's a randomized algorithm that can or you can make it deterministic if there's a deteristic algorithm that can find such a cut very efficiently just by using the eigenvector。

Okay， so we proved both directions last time。And so on the one hand you have an algorithm to find a cut if your secondary is small。

 and on the other hand， if you second is large， then in sum you are certifying。

 you're able to verify that the expansion is large。Okay。And I mean。

 I guess the key thing to remember is that the expansion of a graph is a quantity that's NP hard to compute。

Because。Because essentially it's like。It's a minimum overall subsets of size at most than over2。

 you know， a bru force algorithm would take exponential time and in fact it's NP hard。

So talking about you can say that it's a more complicated version of min cut right in a sense。

 because counting the number of edges cut divided by the volume。And it's in be hard。Okay。

 but it's a very important quality because lets you decompose graphs。And。

The second eigenvalue gives you a handle at this quantity。ok。Okay。

 so that's where we were and we saw proof of this theorem。Okay， so let's see what we'll do today。

So let's understand all the consequences of tis in quite a little bit more firstly。

This bound that we have。Lambda 2 of G over 2 is smaller than phi of G is smaller than square root 2 Lambda 2。

I should just say Lada 2， and when you say lambda 2， I mean Lada2 of the normalized lapplaceian。

It is the lapplian divided by degree。That's what we always。This是。Okay， that's the theorem。

 So now both the sides of this inequality can be tied for different graphs。嗯。In fact， I guess for us。

 sort of the I mean。Like if you look at this algorithmic side the。

There the inequality is tied for a path。We take a path on in vertices。连。You can check the the lambda。

 too。Of the laplaian。I。1 over n squared。Whereas the expansion。Of a part。Theres one over n。

Or I guess order when I in。This is about results order1 or in squared theta。

With up to constant factors。Okay， because this is because if you look at a path， then。嗯。

On in vertices， this pared cut you can pick is right in the middle。You will cut one edge。

And the volume on both sides will be about1 over2。It it's like2 over n， that's the。Spaed cut。嗯。

And the eigenvalues of a path are explicit you can write it on explicitly they correspond to some sort of cosine functions actually it's cleaner for a cycle for a cycle on in vertices you have the same phenomenon the eigenvalue is order1 over n squared the expansion is。

うん。1 over end and for a cycle actually for an end cycle the。

Theen know the very explicit formula for eigenvalues and eigenvectors， in fact。Just the you know。

 when you draw an end gone。A regular endgon in the plane like a regular end gone。

 that is the embedding of the of one of the eigenvectors so you can calculate its eigvalue it will be like 1 over n squared。

嗯。And so this side is tight， there is a square root gap。ok。嗯。Right， okay， so a great question。

 So there's a question of whether there's a related reserve for higher lambmbda3， in fact。

It's a nice question， yeah。嗯。So so like。So we already saw that if the lambda k is0。

 then there are k connected components。So you'd want to know if the same thing is true in a robust sense。

So the following is true。你 guess是铁。In a graph G。嗯。There always exists you know k sets， S1 through Sk。

 you can find K dis joint sets。Such that。All of them have expansion。

Smaller than square root lambda k。So this is so far so good， except you lose another。你诶。Penoin嘅。

Facted。The current result loses a polynom， we don't know if you really need to lose polynomial K。

 it could be lo K， but the current best known thing proposes。

So this is like a robust version of this， we know that if this k eigenvalue is zero。

 then there are a k connected component and this says that if the K eigenvalue is small。

 if lambda k is epsilon， then there must be actually k disjoint sets。

Such that each of them has small expansion。Every one of them has small exp function。

It's quite nice that you ask the question right away because， you know， Che is inequality。

 the two sets on a graph was like from the 80s and this was proved only in。2012 or something。

 2011 or 2012， like probably 2012。So I guess nobody asked a question to that point， maybe yeah。嗯。

And actually， there are。There are like like a few more versions of this chi's inequality。

 but this is the mean。Okay， so this is good， all right。

 so now you know one more thing which we should mention is we are talking about expansion and we already saw an algorithm for expansion before we came to specgraph theory。

And that was this metric embedding see the boardga embedding you solve a linear program embedding21 and so on。

 so if you recall the guarantee of that to us， so this boardga embedding。

Bo games embedding class Seia program。This said that。It finds a set。Yes。With。Expansion。F of。

At most log n times the expansion of the graph because it was a log n approximation。

Like it was a log in approximation to the problem， so you lost a lot login factor。

And the Ches inequality that we just saw just now are the Che's algorithm。That。

It finds a set with expansion。Essentially square root fee of G。Okay， so in a general graph。

 it finds a set set s。With expansion。几续。So Bgas embedding gives you an approximation of login factor multiplicativeily。

But as。诶。This one。嗯。Gives you an expansion， which is arbitrarily large constant。I mean。

 so this one gives you an approximation， which isr can be arbitarily bad。

 but it's a different kind of an approximate getting square root approximation。So， you know。

 if your expansion is speed finds you something like a square root fee。

 so which is okay if fees is like large， if fees are constant。Then you get a constant approximation。

 but if fee is， let's say very small， let's say1 over n。

 then the ratio between phi and root fee is square root n。

So that's the difference between the two algorithms。

But tiga's algorithm and the tis thing is very nice because。Like in a regime like。

Where you care about it gives you a good approximation so a good regime remember we talked about I guess when we spoke about expansion。

 we talked about these graphs called expander graphs。



![](img/10fe05bb1beb4869e3a8daa8954ff4d9_6.png)

![](img/10fe05bb1beb4869e3a8daa8954ff4d9_7.png)

Let me just。Define so is a combinatorial expander。I guess let me。It's a deregular graph。

For some constant D。Such that its expansion is as good as a complete graph。

At least some constant omega 1。吃播知道 one。Something。So that's an expander graph like a。

An expander graph is like a very sparse graph， because think of B as like。Four or something。

 you have four regular graph whose expansion be should be as well connected as a complete graph。Okay。

 in a sense。And that's a combinator expander， so this is a good definition。

 but this this doesn't tell you like how to even verify。

 forget finding one if I give you a graph how to even verify that it's an expander graph。ok嗯。结问。G。

How can you verify it's an expandeder？Okay， and Bgen's algorithm doesn't help you here because it loses a login factor and youre really toward constant factor expansion and if you lose a login factor doesn't tell you much。

 but you can use chiga's inequality to。Verify expansion so in particular。

 like there's an alternate definition of expander。It is spectral expander。Okay。

 what's a spectral expander， it's again a deregular graph。G， such that。You know。

 Lambda2 of the lapplian。I guess normalized lapplian lambda of the normalized lapplian is at least a constant。

Some point， I don't know， 10 to the minus4， let's say something like that。ok。And。

And so this is something you can actually verify given a graph it can actually compute its eigenvalue and check that it's a spectral expander。

 this is verifiable definition。And by Ches inequality， the two are basically the same。So， you can。诶。

You can construct a community will expand。Expandander by actually constructing a spectral expander。

And vice vera。All right， so。And so in fact， when they construct expander graphs， it's much easier to。

Actually， even when you prove things， it turns out to be easier to prove that the eigenvalues are at least a constant。

Rather than proving that the expansion is at least a constant。Okay， so that's。

Is if you come on chis inequality， let me show you another。Okay。

 so which graphs like do which graphs and？This trigger quality work， well， it works。

Like you can use this spectral。Partitioning on lots of geometric measures and things like that。

 in fact， that's how the achieves inequality and spectral partitioning came about that。

You know like the very few first applications were on real mesh graphs and things like that real mes so so let me show you a theorem which sort of proves what that that indeed。

呃。Cigs inequality gives you good cuts on plain aircrafts。So， the data is。For every plan or graph G。

The second eigenvalue。Is it most？Again， always always the。

Always the we'll always talk about the normalized lapplian。Okay， always。So in fact， let's say8 DN。

ok啊。Sos saying that it's very， very small， so for every graph if you have a planar graph。

 it will have very good， very sparse cuts， as you can imagine when you think of a planar graph at least in my mind。

 always think of a grid or sort of like a map or something and it's clear that if you sort of cut somewhere in the middle。

 you should you know get a very sparse cut。But。This is prove that。Okay。

 so let's see a proof I mean I want to show you this just because it's sort of fun theorem to see a proof of there's a it' just a couple of proofs。

 but I'll show you the。嗯。し。There are two proofs actually， and want them。嗯。The earlier one。Okay， so。

All right， so we want to take a planar graph and we want to show that it has a small eigenvalue。

And the natural thing is， you want to prove an upper bound on eigenvalue。Is to exhibit an embody。

Right。Exhibit and embedding as in。What you'd want to do is to assign I guess B1 through VN。

 some positions or vectors such that the rally coefficientient is small。Such that， you know。

Whatever bound we want。Okay。And I want to exhibit some vectors in let's say， two dimensions。

or some number of dimensions I don't care how many dimensions but I have to satisfy this and of course I have to make sure that I don't point like I don't assign everybody the same vector there's always a trivial zero eigenvalue right always for all of these things the trivial zero eigenvalue is assign everybody to the same point so I need to truth make sure that this is not that so and that's the same as saying this embedding is orthogonal to the all ones which is the same as saying that need I need some condition like。

Some， let's say the sum of all the vectors is zero。

This is saying that your embedding is orthogonal to the all one vector。

 orthogonal to the embedding that maps everything to the same point。Okay。

 so this is a way to prove that。Yourr Valley is small。Okay， okay。

 so now where where do you find this embedding well。

 you know let's start from the pro theorem statement， we have a planar graph。Okay。

 so that's good so let's start with a planar graph。

 you have a planar graph meaning you can actually draw the graph on a plane。So， you can actually。

Draw the graph on a plane so that。None of the edges intersect each other， that's a planlear graph。

Thank you。There should be no crossing edges and you can draw it that way。Okay。Okay。

 so that's a planar graph and what is okay so and there are many ways to draw the graph on a plane right。

 So how do we find this embedding we'll use this theorem。诶。

This is from classical I guess drop plain drawings of graphs it's called the I guess it's I don't know I think it's called the kissing circle theorem I think。

 but basically it says that。You can draw a par graph。By。

Or you can express a plan graph as the graph of。In our touching circles so。

What does it say that if you have a plano graph G？Then you can associate a bunch of disjoint circles。

Then there exist disjoint circles。Let's say let's call them C1 through C they don't。

They don't overlap， these circles don't overlap。Such that。IJ is an edge。If and only if。C i touches C。



![](img/10fe05bb1beb4869e3a8daa8954ff4d9_9.png)

Okay， so this is。

![](img/10fe05bb1beb4869e3a8daa8954ff4d9_11.png)

你。I mean， okay， I can。是。Right， so so this is。This picture corresponds to a graph one。4 vertices。

 I guess。嗯。And。I guess the graph here is。😔，It is。Yeah。Okay so that's the graph。

You can draw every planar graph or with every planar graph you can associate a circle drawing like this Okay。

 that's a theorem alright， so this is well okay I I should。Okay， this should be at the center。

 right that we need。Okay， so every plan can associate circles like this， okay。

 what's the next step here？Well， you know， now the centers of the circles sort of suggest an embedding。

Like V1， v2， V3， v4。Okay， that sort of suggests an embedding， but actually you know。

What we'll do now is。On the plane there is no sort of bound on these lengths of these vectors or how big these circles are and right if we're sort of trying to make sure that the edge lengths are small when you're trying to find embedding where the edge lengths are small and on a plane sort of no way to control the lengths of these edges maybe this circles are too large and too small and so on and so in order to control the lengths of the distance between these vertices we use whats we use what's called a stereographic projection so what we'll do is。

Here's a stereographic production， let me see if I can。Try it。So。So if you have a plane。ok。

You can draw a。A sphere on top。that's a sphere on top of the plane and the sphere touches the plane at its tangent to the plane。

And now you look at the point opposite to the。Tangent， which is this vertex。

 lets me call this point x， that's the point opposite to the tangent。And you can take any。It？

Point here on the plane。Any point here and map it to a point on the sphere by。

Sort of you draw you connected。And then you connect to x with this point， V。

By line and it's going to intersect the sphere at some place， let me call that。嗯。

I guess I'm going to call it V prime。So V prime is the stereographic projection of V onto the sphere。

So you're projecting the entire plane onto this sphere。So whatever you're drawn on the plane。

Will get mapped to a picture on the sphere when you do this。Okay， so if you have a line here。

A straight line here。It'll get mapped to something here。Okay。

 and whatever you have on the plane will get mapped here。 so in fact， the if you if you had this。

Picture of the circle embedding on the plane。Okay if you had this picture here。不。

Let's say four little circles。Its some embedding of the graph on the plane。

 when you do this it gets mapped onto a picture on the into embedding on the sphere。ok。

And the nice thing about steographic projection is I guess millions of nice things about it。

 but one nice thing about it is that it maps circles to circles。So in fact。

 each of these circles becomes a circle on the sphere when you do the project。So。嗯。Yes。

Steeleographic projection。Map circles to circles。OkaySo each of the so your entire planar embedding now becomes a planar embedding on the sphere。

Okay， so that's neat so because now you you've drawn your graph by circles on the sphere instead of circles on the plane。

Okay， and the nice thing about circles and the sphere is that， you know。

 they can't just grow arbitrarily big， they're sort of bounded by the sphere itself。

So it's good for us。So now， you know， after you do that， you have。Or which way do it。

You could have picked the sphere and the stereographic projection any way you want。

 whichever way you did a stereographic projection， you'll end up with your drawing of your graph。

On the sphere。Okay。Okay， so now okay， so now we have these vector Okay now， you know。

 you really have vectors in three dimensions now these vectors in three dimensions corresponding to the three points。

 let's say all the。of the graph。For every ver vertex， for every vertex I。

You have a vector VI in three dimensions， which is basically the。Vectctor on the sphere。All right。

 so that's good Okay， so now we are ready to actually calculate this really coefficientient of this guy。

Okay， firstly， let's say it's a unit square so。So if I like what I'm interested in is in the。

Recall that we'm interested in the rally option。S VI minus Vj whole squared Ij in the edges divided by d times。

Someur right non V I squared。Okay， that's what we're interested in。 Okay。

 so now let's look at the denominator first。 It's the easy thing。 So the denominator。Is。

Easy because why， because each of these vectors are a unit vector clearly because they're on the sphere。

The unit vector， so therefore the denominator summation norm V squared。Is N。

 So D times that is D times n。Right， so that's easy。So that we got the denominator already。Alright。

 so now let's look at the numerator。So the numerator we to look at the distance between these。Edges。

 okay， so if I look at the distance between。VI minus Vj。All right， so so these are。No。

Note that there's a circle or there's a sort of a spherical cap or a little circle on the sphere for both INj。

The little circles are touching each other。So the distance between V and Vj is at most。

The radius of the two circles。Addd it up together， R plus RC。With all right。Is the radius。Of the gap。

So here I guess I need another。I guess I need a picture to。Sort of show what what I mean， so。

So if this is a sphere。And if I have a cap。做。If I have a cap。Little spherical cap。

 then the radius of the cap is the distance from。The center。Do。The edge。

that's what I'm calling the radius all right。Okay， distance of the center of the cap to the edge that's RA and you have R plus R。

 this is just triang in equality。And because the circles touch。Okay， that's。Allect， So now therefore。

VI minus Vj equal squared。Is。At most， whatever R+ R holds squared。

And this is at most two times R squared plus Rj squared。Okay。

 so we get the distance between two touching circles。

 the square is at most2 R squared plus2 r squared。Okay， this is for every adgizer。All right。

 so now if I add it up over all the edges。Some over all the edges。This distance。

What do I end up with， I end up with。Two times some over all the edges。Of R squared。Plus R J squared。

几能 sir。😔，我出嘅。And。😊，Each vertex is counted D times in this sum， right？So， this is。嗯。

I guess 2 d times sum over I or I squared。That's what we want。

We get so we get 2 D times somei R squared。 that's。Numerator。Okay。

 and now we need to bound this quantity。Need to bound。S of I squared。

 the sum of squares are these sectors。ok 啊。And， and then the。Okay。

 we want to bound this sum of squared for these ideas， yeah。And。Okay， so how do we do it well？

Any ideas why how we would do it？Yeah， so the so the thing is to try to do the area， right？

 So what is like， you know， these are disjoint circles on the sphere so。So the。

Area of the sphere together is four pi is at most four pi。Okay， and this is area of the sphere。

So here the sphere is equal to4 pi what I'm saying e of the sphere is equal to four pi。

But this is at most the sum of the areas of the caps。Okay。

And what is the sum of the areas of the caps， Well， actually it is sum over I pi R squared。Okay。

 and this gives you that。嗯。Sum over I R squared is at most four。Oh yeah， thanks。

Areas of the sphere is at least some of the areas of the caps and set by R square atspher and so now you substitute back in here。

 you'll get the bound。嗯。你 getた。You can get that the ratio is actually right。So the ratio。

 some over V I minus VJ。Whole square I is an edge。By D times some over I V I square。嗯。

I guess I'm getting a better bound than what I promised， but that's fine。I'm so I'm getting。Doり。

Times to 4 divided by。Oh。D times n。So we've got8 over。Yeah。

 x is a over you don't need a D if you're using normalized rep plus and you don't need a D。Connect。

Yeah yeah。To that to。I guess like one，1。One place where I cheated a little bit。

 I said that the area of the cap is R squared。PiR I squared。 This is actually true。

 but it's an it's a。This like， you know， it's a little bit of an not fact。

 it's not obvious that the area of the cap is p square because we recall that we are talking about a cap on a sphere。

 and I'm saying that the。嗯。The radius is the distance from the center to the edge of the cap and that's actually also equal to piRri squared。

 you can check it so yeah。Okay so that's one fact。 I guess the key fact which I pushed under the rug or we haven't yet work worked out。

 Okay， this is a nice embedding at all。 How do you prove that it just doesn't map everything to a single point I mean more。

More carefully， how do you ensure that this is zero？He sum or I VI should be 0。Okay。

 how do you prove this This actually has a fairly subtle proof and it's very interesting and subtle proof。

 The key point is that。Like there's a lot of flexibility in what we did now right if once you drew the planar graph on the plane I could pick the sphere and I could pick any point to apply this stographic project projection from I don't need to geographicgraph projection you can a lot of flexibility on that so there are a lot of different embeddings on the。

Circle that you can get by doing this geographicgraph projection and what you really want to prove is that there is some way to do a pick make these choices so that so that this is actually true somewhere I got one trend via is zero。

Okay， and。There's a very nice proof of this fact， it uses prowest fixed point theorem and ideas from topology。

 but it's probably too much fun for this class， but you know you can look at it in at this。

The notes that I know that I linked to this Spman selection notes。

 it has a sketch of like I think it has most of the proof that for some technical details。

 you can look it up its browse fixed point theorem。And you use it and you do it Okay， so that's。一撮りる。

Okay， so this is a proof that trainno graphs have this property， but you know。诶い。

This is a very clever proof， but theres a proof the different proof。Of this and。

All more general facts like even if you draw a graph on a tarus， for instance。

 that must have a small eigenvalue or right you can draw on a graph on any surface with a small number of holes even that must have a small eigenvalue there's a general proof that gets that and even that's very nice and clever and very nice yeah but that was more recent。

Maybe from yeah 10 years ago， this is my a little bit older。谢。Okay， any questions？Yes。

 so actually it's order one over in yeah。嗯。Exhibitive engineering yeah thanks and this this should be order one over yeah we can actually do one over yeah。

Because I guess I'm using the normalized laplaian。I'm getting order one already。

Your distance metric like VI minus VJ distance like is that is that a spherical distance or is that like the our three distance or like yeah oh this is right so this has to be the L2 distance。

Yeah this has to be the L2 distance that's the like that's the only way this will like it will certify the eigenvalues so if you're only a cerify eigenvalue you have to use L2 distance or in r3 it doesn't matter whether it's on the sphere or thing but yeah we use the actual L2 distance here yeah I should be clear this is a triang in quality on L2 and that's why we actually sort to the actual distance from the center to the edge。

And RI and RJ， are they radiuses in O2， are they radiuss of the sphere？

Rdiusus in L2 yeah so this R is actually the distance from this actual L2 distance from the center of the cap to the edge。

Not on this sphere， but actual distance in L2 like the length of discardord essentially。

 and in fact that's why this is also a little bit of an non trivial fact。

Like the area of the gap is actually equal to pi squared。And then in this case。

 RI is not the radius over the sphere， it's the radius in the plane of the circle。

It's the radius I wouldn't say in the plane because you don't want to I mean radius in like it's really the distance like if you had the sphere in three dimensions。

 you took the center and took a point on the edge and you measured the actual distance equal the sphere that's the。

Yeah。呃。Yeah， and I don't think you can flatten the cap and things like that because the area will change if you try to flatten it。

好啊我我系可意使佢。Like yeah， if you flatten it， I think you'll get， you should technically get a long。

I mean I't know what should happen with you shouldn't。Yeah， I don't know how you'd flatten it with。

 it you need to be flatten it in a way the area remains constant right。

 because you're really interested in the area of the gap。So。

But you know there'ss a I mean it's it's easy if you want to actually figure out what this is you can I mean it's basic like some integration right you just integrate something and you get the answer it turns the pi squared it's fine apparently it's ourimes。

点有我出定。Itsact committees， someone， yeah and it's the exact committees。All right， it's good， okay。啊。

Any questions？Okay， so I guess there's a question on how common is use of stereographic projection。

 Well， stereographic projection is it's extremely basic in。Complex analysis and。Also。

 I guess in topology could say， but I've never seen it used in computer science。Apart from this。But。

 you know， this is like in complex analysis， you know， it's like。Yeah。It's always done a rather。

 you know， yeah。And even in topology， this is this is in some it's called I can it's called I guess it can be called many things。

 but one， one， one thing you could call it is the one point compactification of the。Of the plane。

 the plane is not compact， so you add a point at infinity and wrap it around and then becomes compact。

そううん。This is like one yeah。Okay， so that's good。 Okay， so let's。嗯。All right， so after this。

 I have to decide on what to teach and I have a couple of many different options and。

It should stack something。That we can all collectively forget over spring break and it'd be okay that's the。

Okay， let's let's do let's do some， okay， let's do something。 Yeah， Okay， let's do this。All right。

 so this is good。Okay， so。嗯。嗯。Okay， so。So。So one important consequence of expansion is mixing of random walks that random walks mix fast when you have expanded。

Let's talk about random walks。So let's do the simple things we have a let's in the most simple setting。

 we have a G is a deregular graph。Okay， and what do you do in the random work。

 you started a vertex v。And， you know。We and， you know， just random workers at each step。

Pick a random neighbor with Pro 1 overD and go to that neighbor。

It is steep each step if you're at vertex you pick。An LGUV with probability 1 over0。

Because they're at DHs and then move to weak。Gives in the most natural thing。嗯。Okay。

 so it's a natural process on a graph， right？呃。第。So let's understand how you know what happens to this vertex as memora。

 okay， so let's say we start with let's say suppose we start at vertex U。Okay， start the walk at you。

Okay， and the way we keep track of the work is lets let's look at， you know。

 if I start the work at you。And then if I， after some these steps。I can clearly be it。

Any lot of different places depending on what random choices we made。

So what is more interesting is to， you know， we can keep track of the probability that we end up at any given spot。

Okay， so let me define。比ace of地。Of v or p sub T of v is a probability。That the walk。Is at we。After。

These steps。Okay， so piece sub P is a。Okay， what is P of T， it's a vector。

It's a non negative vector in。It'ss the n probability， it's a non negative vector。

 and of course this vector always adds up to one。Like the entries of this vector always add up to one。

Okay， so far， S。And。So that's good so we have vectors and P0 is， of course。

 what we started off with the initial probability distribution。

Is actually just let's say we started out with at a single vertex。

 then the initial probability distribution is one net third vertex and zero everywhere else。

It'll be one。If v equal to U， like the starting point， zero otherwise。

So you have an initial product distribution at time zero。And at each step。

 you have a new product decision P sub。Okay。Okay so。You know。Right so the probabilities。

Sa for nice linear relation， its a probability that Im at at we。In9 deep。

If I had to be at V in time T in the previous step， I should be in one of the neighbors。Right， and。

From that neighbor， I should take the edge。嗯。Leading to this vertex。So in fact。

 the property that you're at V in time T is actually sum over all the neighbors。

Of the probability that you are at W。In time t minus1。Times1 over deep。

Because what is the one of a D chance that you come to So in fact， in terms of our definition。

 P sub T as a vector。Is equal to。1 overD。Times the adjacency matrix。Times P sub d minus1。Okay。

 theres a if I write this as a matrix vector thing。

 so the product distribution after T steps is like a 10 times the ad matrix and pro distribution after t minus1 steps。

so that's。So this is no。This is really the only key thing， right？In all of this。So， you know， if I。

For simplicity， if I call this matrix。Itilda。Okay， right， so we have P of T。

Is equal to a tilde p sub t minus1。Okay， and then of course you can use it repeatedly right and you say。

 oh， it's a tilda squared piece of t minus2。Right， and then。So you get its a tilde to the T。

Times the initial vector p0。So we have an explicit expression for the pro distribution after T steps okay。

 and this should remind you of。I guess one of the homework problems on like。

Some sort of averaging operator power to the mask the averaging operator。

 it's really exactly the same averaging operator。Its it。Okay， and。

Okay and and you know so now you can ask， okay， how far how many steps do I to take before I've sort of mixed mixed as in the P of T distribution is uniformly random vertex in the graph。

Okay， so。So let's say， you know， epsilon mixed。let's say Epsilon mixing time。Is the number of steps。

After which。For the smallest time after which， let's say the piece of T。

Is very close to the uniform distribution well the uniform distribution corresponds to the vector one over n everywhere right so it's says one over n times the all ones。

That's one over and everywhere is the uniform distribution and I want this to be close and you know you can pick any norm to work with here so let's just work with a two norm。

Okay。Okay， that's this is saying that how， yeah。After what is the smallest time after which your endpoint looks fairly random okay and。

You know， when we say this we have to quantify， one thing we have to say is what about the starting point right maybe if you start sometimes you start it at the right place。

 your random walk mixes faster than if you start at the wrong place。

Right so just to give you an example。Okay imagine you have a complete graph like this and you have a path。

嗯。A little path， right， if you start here。There's actually you know， you will。

You know you will sort of reach everywhere quickly as opposed to if you start somewhere in the cek。

It's very unlikely that you will actually。Reach this part and follow this path。Okay， so。是。ok。Okay。

 so now let's see what let's see how you know， let's see let's calculate how this distance L distance behaves Okay。

 so we already have P sub T。Is equal to a tilde。Instead of writing A' me write1 over D。

Times a times p， is it p sub t minus1， Okay， we have this。We have this fact。Okay。

 now actually I'll subtract all one's vector from it。If I look at this vector。It's actually equal to。

Okay， this is why is this true？This is true because。Because a times all one's vector。

Or A or d times all ones vector is equal to the all ones vector。

Well all onesvector is an eigenvalue is an eigenvector with eigenvalue  one。And therefore， I mean。

 alternately， if you start with the uniform distribution and you start you take if you pick a uniformly random vertex in the graph and you take an edge。

You will be at uniformly random vertex in a deregular graph。

Okay you can check this by hand that a times1 is equal to one。Okay，8 or times。

 so therefore I can write this equation， so now， you know， in fact， I have this property now。

Not just P of T， but actually the deviation from all ones also satisfies this property。

The deviation from all ones is equal to this matrix A over D or I guess we were using a tilda。

It turned的 to the D。Times the original deviation from all ones。Okay， so this。

So the deviation from all ones also actually you know。

 behaves like as if you're multiplying by this Ailda。Okay， and。呃。

RightAnd we saw what happens to vectors if you keep multiplying it by a matrix。

 so this is something which is sort of very important to like it's a basic fact about linear algebra but just very important to sort of internalize this because shows up all the time is if you have vector V and then if you take a matrix M。

 let's say real symmetric matrix for simplicity we have real symmetric matrix。

Right then if you're interested in m to the T times v。Well。

 you can always look at this as sum over I lambda I to the T。Times。嗯。V in a product EI times Ei。

 where Ei is the i tagagon vector。Lambda is the i tiagon value。So。If you give me any vector。

We if I write it in the eigenbas。Okay， then each component gets multiplied by lambdai to the T。

This actually showed up in this power to the masses thing， right。So in fact。

 we in our situation here。We immediately get。VN minus。1 over and all once。

Is actually sum over i lambda I to the T。Times the initial component。Along all ones。

So let we just call that CI， it doesn't matter。C系。Thanks， yeahang， like convicted。

Okay this is just true and so now you see what's happening if all your lambmbda I well lambda I is the eigenvalues of ailda right Lambda I is lambda I of8 tilda。

Okay， so if all your eigenvalues are， let's， let's say less than half。えIf。

Or lambda I of a atiilda is less than 0。9 every component is exponentially decreasing。

In this difference， you get 0。9 to the t and so therefore you're getting a closer and closer to the albans vector exponentially fast。

That's basically what's happening， so if your eigenvalues are bounded away from one for the decency matrix。

Then you converge exponentially at an exponentially fast rate towards the uniform distribution。

 mean within log n steps， you should expect to converge to the uniform distribution。

Order login steps。And really， the second eigenvalue or the largest of these lamb dis controls how quickly you converge to the uniform distribution。

So in fact Ive。If I had to write this， I'd say Pn minus1 over n times all onces。The two norm。

Is at most。And just。Yeah。let's say N。Times max or I。Lambda I to the T。It just used this bone。嗯。对呀。

Okay， this is just because。Like here， I mean， I guess I should be， you know， it can be a little bit。

 So basically you know， your p0 minus1 over n times all one vector。This vector has lent at most one。

Taking immuno it's atmost one。Because it's the probably distribution right the worst thing you can do is p0 is 1000 and you get length at most one。

 therefore summation C squared is at most one。Smission say squared is at most one。

basicallyically you start with the vector whose length is at most one。And therefore。

 you will end up with。They can exponentially small。Distance。So actually。

 sorry I don't even need an end here， what amm I saying I don't need an。出日。Okay， so so。Okay。

 so this is it so now you know you can get a bound on the epsilon mixing time right so the epsilon mixing。

Is。Is basically。嗯。Right， it's the。It's the T at which that summation Lada to the T is less than epsilon。

 so it is log one over epsilon divided by。Log。Of the max。どラ。And let me be clear against them。😔。

At the in matrix we're talking about。Okay， that's。这是这你。Yeah。

 and we are talking about the adjacency matrix and always you can convert this to lapplian right because in a de regularular graph。

 the normalized lapplian lapplian is actually equal to D times  serity minus adjacency matrix。

 so the lambda I of the lapplian is actually d minus lambda I of the adjacency matrix。So。

So there's a small you know。You can it's a convention， you can either work with a matrix or lappl。

 if you talk about lapplian then usually you talk about spectral gaps and here you're talking about gaps from one。

Gaps from D because D。Anyway so。Get this and。Any questions on this？Makes sense。

Well professor for the previous page。Why just say like PM N minus like1 over n shouldn't it be P。Oh。

 thanks， thanks， Yeah repeat。Yeah。Yeah。Okay， so if you had two different connected components。

 then the maximum liigenvalue wouldn't be affected by that。 right。

If you had two different connected components。That's right。Yeah。

 I mean this formula will fail and the reason this formula fails is there is there is a。

Eigenvalue of I。I again value one。 So lambda I of。So actually let me be let me just write the whole thing in terms of the lapluian。

 so basically in the lapluian we have for the normalized lapluian you have。In meigenvalue。

And we said well always。Order them in increasing order like this。

and these normalized lap plus eigenvalues， they start with zero because there's always a trivial eigenvalue which is zero。

 and then we go up to the value of two utmost two。系。

And this formula in terms of the normal is lapplian is log。1 over epsilon。Divided by。Log。1 minus。嗯。

Lambda 2。I guess I should say。Men， right a mean。minlo。Okay。

 so so effectively what happens is that the mixing time the value blows up in this expression because you have log of one in the denominator log of one will be0 and you get ining yeah and it makes sense because if you start at one of the components you'll never reach the other component so in fact there are。

えう。I guess if they you use terminology from mixing random walks。

You call a distribution a stationary distribution if it doesn't change when you take a step。

So on a connected graph， there's just one single stationary distribution。

 which is uniform distribution， that's the only stationary distribution on a connected deregular graph or a unique connected graph。

This unique station， but if you have two components。

 there are two different stationary distributions you can be in this component uniform lit random or you can be on the other component uniform lit random both of them don't change when you take a step。

And yeah， so that's a good point actually this expression is is bounded only if the eigenvalues are。

Not exactly equal to one right or or the second if the second eigenvalue is0。

 then this expression blows up because log of one is0 and blows up and which makes sense。Yeah。

 so actually this is only for a connected graph。Otherwise， the thing is infinite。Okay。

And what else about this？Yeah， okay， so this is good and let me do one more thing， okay what okay。

We saw that if you're an expander， the eigenvalue is like a constant。

 so you'll get very quick mixing like log n mixing， but let's do the case of。A general graph。

If I give you any connected graph。Let's hit D regular。Okay， what does chiga's inequality tell us。

 chiga's inequality tells us that lambda 2。呃。Square root lambda 2。Is at least the expansion。

Of the graph。And so Lada2 is at least。Phi of G holds squared by 2。Okay。

 and if it's a connected graph。If it's a connected graph， no matter where you cut。

 you'll cut at least one edgech。Okay， at least one edgedge will be there crossing。Okay。

 and so the expansion of a connected graph。Is at least one divided by。

The total number of edges in the graph like D times n。Because you need to cut at least one edgech。

So therefore， you get a lower bound of at least one over。嗯。有226色。

Lambda two of the normalized lap Lambda two of the。Yeah， and know。That's right。

 So at least one edge and divided by Dn。 so one over Dn squared。So you get order one over dn squared。

Okay， so you get at least like you know， a polynomial gap， like， you know。

 if days is a constant is one over n squared right？Okay。

 so what that means is you'll get like this theorem will say that the L2 distance。

Pt minus1 over and all once。嗯。Right， this converges。To uniform。In Le and polynomly， many steps。

It is an epsilon in like some tea， which I think you'll get。嗯。Yeah。

 irllig get polynomial in many steps。Okay， so like I think you can get N cube steps basically。So。

So okay， so what are we getting in any graph after N cube steps， you will be。

You'll be close uniform in any graph。As long as it's connected， you'll be close to uniform。Okay。

 and I guess let me get to where I'm going to， I guess the punchline is。

E I guess this is one of the earliest randomized algorithms that was discovered is a randomized algorithm to solve connectivity。

Randomized ST connectivity in a graph。Okay， this is a simple question。

If I have a graph and I give you a word X and a T and I ask you， is S& T connected？是。Okay。

 of course this is easy， you can run the extra breakfast search， whatever you want， depth for search。

 all those things， but there's another algorithm which is just done a random walk。

For some like large polynomial steps like n to the five steps it would suffice I think end like NQ log n might suffice。

 but let's just do end to the five steps okay。And。You know if you see， start from S， start from S。

Start from S， run the random walk for end to the five steps and if you see。第。Is say SNTR connected？

Otherwise， sayNT are not connected。Like they are in different connected components。Okay。

So it's an algorithm right it's a very a silly algorithm just a random walk and it's a randomized algorithm to solve connectivity。

 but the nice thing about this algorithm is it needs very little space。In fact。

 you don't like usually in a breakfast search or breakfast search and so on。

 you need order in space because you every time you visit a vertex。

 you have to mark that you visited the vertex like you need omega and space in all of the algorithms that you use because。

You have some kind of a marker you're building a tree and so on。

Here your only thing you need to know is。Like you have the graph stored somewhere。

 the only memory you need is。You need to know your current location。

Because you want to running a random book and remembering the current location is only log n bits。

 so it's actually login space algorithm。So this is an order login space algorithm to solve ST connectivity。

You also need to know the transition function， how do we access that？

You have the graph so so right so when you define log space algorithms we have to define it carefully what we'll say is the input is written somewhere input is written on a tape of during machine you know input is there in part of memory which is not you can't edit it it's just input is written read on the part of memory there's n bits n bit input or in this case so n squared bit graph written somewhere and you just read the graph and do the transitions so you're at a vertex you know you read the what are the neighbors of the vertex and you pick one of the neighbors and you go there。

I see and so this takes on the log in space and it was like a very。

I one of the very basic open questions in complexity theory， not most less so an algorithm。

 but complexity theory， whether you need randomness at all for algorithms and in particular can you take this randomized algorithm and can you have a deterministic algorithm that only uses log in space？

Can you have a deterministic algorithm to solve S2T connectivity in log less than login space and the answer is yes。

 and it is a very nice algorithm， which is I guess Disc in 2005。Its like。

Log in space algorithm for connectivity。I guess another thing you need to remember is how many steps you have walked here。

 that's another counter。Which goes from one3 into the five。

 you to remember that because you would have when to stop。So that's another counter。Yeah。

 so but there's a a deterministic algorithm we also use log in space。

 it uses a lot of expander graphs and it's a very beautiful thing。ok I定嘅。Stop here。😔，Yeah。Okay。Yeah。

 so for the mixing time analysis， yeah， is。The one is technically an eigenvalue of A over D right right right so I should say。

Yeah， I should say I greater than one， right？Like lambda， less than one， like only the。

Not the top eigenvalue， yeah。Yeah， that's right。Thanks， yeah， and that's because p0 minus。

Like you're always working in the space that's all going to all ones。

You start with the vector's ultimate ones and you stay in that space because you're ultimate ones always。

Yeah。Yeah， and I think this is actually also I think this also happens in that homework problem the same sort of a thing。

啱未嚟。Oh， this is shooting a randomized algorithm。You know hash tables can use sort of a dictionary problem in like you can do things in constant time right but that's randomized so for a lot of like practical problems like maybe you need a hash table to do things let's say like in linear time let's say a simple problem like you have an array you want to check if two entries sum to a target and with a hash table it's easy to make that like do that linearly naively maybe you can only do n squared like obviously is there a way like if you can do let's say like I know like T of n time algorithm assuming like a hash table does things in o of one time can you transfer that into a deterministic like T of n time algorithm。

Right， actually I great question。Yeah， so。诶。But I guess。I mean。

 I think it really depends on the particular problem at hand， but in complexity theory。

 theyre more like the kind of they're asking even more basic questions like like for example。

 there are if you can solve a problem in polynomial time with randomization。

 can you also solve it in polynomial time without randomization？

Right so so if you have problem we can solve polymer time with randomization so it's sort of very coar like let's say I give you more like bigger polyno you can solve problem in square time with randomization can solve it in some poly time So that's like it's a very basic question first and and there the belief is that randomization doesn't。

Help beyond the polynomial factor as in anything that you can do in randomized polynomial time you can also do it in really polynomial time and similarly log space is another thing whatever you can do in log n space and randomization can you do it in login space without randomization that's another question So these are very coarse questions at this moment like there are particular problems and if you look if you look very closely like you know what's the runtime is it n log n or N log square n then it's it's no longer I mean true or it's not even believed that you can always。

I mean， randomization， randomization will help。And there are cases where removing randomness will make it little less efficient。

Or even maybe even polynomininly less efficient care。But but I guess this is， for instance。

 a big open question in the area right now， which it seems within reach。

 can you whatever you can do in randomized lock space。

 can you also do it in deterministic lock space？Right， and。That corresponds to some。

The restricted form of connectivity in directed graphs that you need to show。

So that that's a BPP versus P right BP versus P is randomized polynal time versus data polyno time。

 this is RL versus L， this is randomized log space versus the lock space。Yeah。There are two， yeah。

 I guess there are two things that B equal to P， I mean， it's believed that B is equal to P。

 it's not yet completely clear， but many people believe that RL must be equal to L。

Okay there's another question about my choice of n to the five yeah I was being a little sloppy here it really comes from using this bound on the mixing time and the bound on the eigenvalue which is one minus one over n cube one minus one like we have bound on the eigenvalue which is。

Eenvalue the lapplian is at least one over。D squared and squared。

 which means the eigenvalue of the adjacency matrix is at least。Or is at most one minus。

1 over d squared and squared。And then you substitute this here。

 I think you can get something better like N cube and so on。I think NC is what you can get。

 but I was being sloppier as I the five。Like， I mean， one thing， you know。

Like you also want me to do union Bo and everything so。Because you。内。

All you know that after Epsilon mixing time steps， you are a uniformly random vertex in the graph。

But a uniformy random vertex might not be T， the vertex you care about， but then you say。Oh。

 but it could have been t， a uniformly random vertex is t with Pro 1 over n。

Okay so each time I'll hit t with Pro1 over n so if I repeat this experiment。

 let's say n log and let's say n squared times， I should hit t at least once with very high priority and so。

Yeah。But we'll do this analysis of this this thing cover time of a graph， we start a vertex。

 how many steps before we cover everything more carefully using effective resistances。

 hopefully when we come back from spring break and talk about effective resistance as electrical networks then yeah。

Yeah。Right as long as T some polynomial we are okay like all we need to what we're trying to prove here is that in polynomial time you you can reach T with high priority。

 you can reach the vertex T with high priority and yeah。So about hash tables。

 do we not know whether there's a way to make the hash table deterministic？



![](img/10fe05bb1beb4869e3a8daa8954ff4d9_13.png)