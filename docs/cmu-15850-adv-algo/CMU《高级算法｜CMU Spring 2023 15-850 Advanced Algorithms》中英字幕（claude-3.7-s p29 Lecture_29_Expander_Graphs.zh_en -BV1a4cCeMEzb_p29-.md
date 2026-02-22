# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p29 Lecture_29_Expander_Graphs.zh_en -BV1a4cCeMEzb_p29-

应 guess。So， welcome back and。To this sort twopart last lecture and it's going to be about expanders and high dimensionional expanders today we're just going to be talking about expanders if time permits at the end we might talk about the definitions of high dimensionional expanders fairly simple ideas but there's a fair number of definitions so it's good to see them a little bit before you actually dive into them。

咁。So good， so what's an expandograph？So in the rest of this lecture。

 I'm going to be talking about G is going to be an undirected。

 always undirected in this lecture unweighted this。It's kind of easy to get rid of。

 but somehow it gets a little more annoying and most of the lecture I'm going to be talking about the regular。

😊，Graphs， so you will see places where the deregularity is I mean it's not really essential。

 it's just as convenient at times。😊，Okay， so this is a graph and this is represented by adjacency matrix。

😊，啊。Which has zeros on the diagonal once for every edge that's present。And it's an adjacency matrix。

 so it's in 01 with the N cross n。Wherein has a number of vertices。

And so it has it's a symmetric matrix and it so it has。For spectrum， so it has got eigenvalues。

 these are real eigenvalues。Because of the symmetry of a。

 and let's say that it's got a eigenvalue lambda 1。Which is。At least lambda 2。

 which is at least lambda n。And I said the graph is deregular。So each row of a has d1s。In in that。

And so this one is going to be D。So the highest eigenvalue is going to be D。嗯。And you know。

 some of this we did back in one of the lectures where we talked about Laplaceians and things like this。

😊，If you look at the eigenvalues of the adjacency matrix。

 the highest eigenvalue is d and this is achieved by the eigenvector。😊，Wwhich is the all ones。

 or if you want it to be an eigen， you know， it's a unit eigenvectors。

 then you should scale this by square root 1。对。Another fact that we saw in the previous lecture is that if the graph is connected。

😊，If G is connected。Then Lada 1 and Lambda 2。Are distinct from each other。That is。

This eigenvalue has multiplicity 1。And it's actually not difficult to show。

 but maybe I'll leave this for right now you can show that lambda n is going to be at least negative d。

😊，So notice that the sum of the eigenvalues must be equal to the trace of the matrix。😊。

The trace of the matrix is0。So there must be negative eigenvalues。And in fact， lambda n。

 you can show that it's no。Smaller， I mean， is's no greater and absolute value than lambda 1。

it's actually at least negative D， and here is another factor that you can show if you want it。😊。

That equality if and only if G is bipartite。So you can actually check for bipartiteness using the spectrum。

In fact， there are algorithms for max cut that use the last eigen vector。😊，To do smart things。

I'm sorry。First one， yes， so this is different only if as well。Yeah。嗯。Yeah。

 strict and only if G is connected。DH is coming out of it， absolutely。Okay， good。

So given this this thing and we alluded to this a little bit earlier。

 I'm going to define a notion call。😊，The edge expansion of a graph。So an edge expansion of a set s。

 now I'll denote this by phi of s。Is。The number of edges going from S to S complement divided by the size of s。

So the picture I have in mind is I have a graph。I look at the number of edges that are leaving S。

And I divide this by the size of this。😊，This is the edge expansion of a graph。

And it's kind of capturing like。What fraction， Okay， so so it's basically somehow saying that look。

 this it's a normalized cut value it's often you know。Normalized cut。对。

This is the edge expansion of a particular set and the edge expansion of a graph is the min。

Overall sets of size n over two。Of the expansion of this。To notice that， of course， this quantity。😡。

If you didn't take the min only over small sets， this quantity would get smaller and smaller as you've got more and more of the graph because you know if s if there was a single vertex sitting out here。

 then this is n minus1， theres a single vertex so this could get very small so this is saying for all sets which are at most half the graph how fast this is expanding。

😊，How many ages are leaving it？ this is called the edge expansion of a graph。😊。

A very closely related quantity。😡，This area abounds in definitions by the way and all of them are pretty much similar to each other。

 but they are slightly different so let me define one more notion。😊，Which is going to be。

When we named for us， it's called the conductance of a graph。😊。

And so now I can define the conductance of a set s often conductance is written by a lowercase fee instead of an uppercase fee that distinction is too subtle for me to you know I always get confused so I'm going to write h as the conductance h or s is the。

😊，Number of edges leaving2。The sum overall ver seasonness。Of the degree of me。

This is just saying look at all the edges that are leaving that are touching this part of the graph。

😊，What fraction of these？Go across。咩。Where an edge remaining in this part if counted twice。

 one for each endpoint。😡，对。😊，In our case， because we are deregular， this just becomes equal to the。😊。

D times the size of s。Which is very convenient， it's just a scaling of this。

But this definition you can use you know more generally and this is where these things start to differ and h of G we can again define as men over。

😊，Over s such that this this quantity， which is often called the volume。

Is less than the number of edges of et of Fs。This is often just called the volume。😡。

You think of every edge of a pipe and this is the total volume of all the edges that are hitting these。

😊，哎。For us， if you don't have to worry about the distinction between H and phi。

They're the same up to this scaling by。对。Not minor things。😡，This fee。A at most D。

And edge effect most。Yeah。It's a number between zero and one。行。A graph is an edge expander。If。

The conductance。Of this graph。Is at least some absolute constant。So， really。

I should be saying a family of graphs。For an expanding family if。

All their conductances are bounded below。By some constant independent of the。And。对。

And very often we'll say something like， you know， G is an。Epsilon expander。If H of G。

You that he steps well。没有。And I'll notice that I've dropped。😡，The edge expander， epsilon。

 edge expander， you can define vertex expanders， I'm not going to do that。Good。

What is an edge expander， what are examples of E expanders？啊。

So interestingly enough these are you know， it's not completely trivial the complete graph is an edge expander you can show。

😊，Theyre in a complete graph。The complete graph is n regular。😊。

You can show that look how many vertic sees so if I take any subset of s n over  two lets say which is going to be the worst case。

😊，How many edges are crossing it about 10 squared over 4？

Out of how many edges were hitting this side， its approximately n over 2 times 10 minus 1。

So this is something like onehu。Complete graph is a very good expander。😊。

What's another good expander？就。What's that？Hypercube， okay。

 so how good is the hypercube with an expander？😊，So it turns out that the hypercube。

 the worst thing is you slice along a dimension like this。😊，The number of edges crossing。Will be。

2 to the let's say this is a D dimensional hypercu D dimensional hyper cube。

 the number of edges crossing will be 2 to the d minus 1。

Because you know half the there are two to the the vertices in this。😊。

Half of them are on the left hand side， half of them are on the right hand side。

Each one had an edge going across， with the matching going across。And what's the？

What's the total number of edges hitting the left hand side， it's 2 to the d minus 1 times d。

It's a one over D expander。Not bad， not great in the sense that as you know if if you take hypercu the fire and higher dimensions。

 this expansion is going to zero。😊，是更成。可以。What's good or bad？Good。

 so what I want is I would like to be able to say that， you know， I can generate a family of graphs。

😊，One for every n or one for for infinitely many n。😊，N vertex graphs。

Such that their expansion is lower bounded by a constant。是啊。

Why because of you know I'll give you some applications for why we need expanders for instance。

 if I have expanders I can de randomize I can de randomdize algorithms。

 I can come up with error correcting codes。😊，I can do things that Jason Lee was doing earlier this morning he was he was trying to break up a graph into expanders and then run good algorithms in each piece。

 etc， expanders are magical objects by the way。It's remarkable how many times it comes up。

At at the end， when when we are just chatting， I'll tell you about one of the first users of expanders。

😊，To build something called a sorting network。This is a network where you plug in a bunch of numbers at one end and they come out sorted at the other end。

 you can say how many gates do you need to build a sorting network？😊，Lower bound is en log n。

Upper bound is also analog logian。But for the longest time。

 we didn't know how to do N log n we knew only N log square and。

And then these three Hungarian mathematicians， they use expanders in some brilliant way。😊。

So it's surprising， you know， once you have this under your belt， this yeah。😊，no啊。好。た。同意他的。

Absolutely。Why did I give both？W。8。It depends on so right now just keep this guy around。

 I like this slightly better because it's a number between0 and1。😊，嗯。😊。

This guy it sort of the notion of edge expansion is very clear it's like you know a set of vere。

 the number of edge is coming out， so perhaps the two like I just keep these two in mind there are a couple of others that I bring into mind when I need to。

😊，But。Just pick your favorite one， you know， you can move between these guys。Other questions。对。嗯。

就是 all的。That just like。is that girl from desk。US itself。Right， exactly。

So this is just this is the sort of natural notion of expansion。

 I look at what set of what is that I see how fast it's expanding。😊，Yeah。Good。Moreover， okay， quick。

😊，So this is the epsilon expander and then the question is how do you build epsilon expanders in particular so heavy the theorem？

😊，A random。呃。A random graph is an expander。Is an expanded。

With high of course I'm being vague out here so maybe I should put quotes around the theorem I haven't given you any parameters of these things。

 but in general this is the sort of things that you might want to keep in mind。😊，And later on。

 we'll try to make this a little more precise。But maybe as I'll point you to exercise people have of take a random three regular graphs。

😊，You need to make sure it's connected so may take three random matchings。Yeah。Take in vertices。

 pick a perfect matching， pick three perfect matchings， it's an expander with high probability。😊。

There are deterministic constructions of expanders as well。

 and this has been an object of study for a little while。

 there exists deterministic constructions of expanders as well。😊，Was there。😊。

Take deep perfect matchings。That's one way of doing this you need to be a little careful because you might get parallel edges。

😊，诶 because if yeah。if I didn't care about that way。嗯。No。But I'd have to， okay。

 let me think about that。They exist deterministic construction， let me give you。😊，Actually。

 let me not give you a determin let me give you a deterministic instruction， take all the numbers。😊。

They take finite field of prime order， connect every element。嗯，X。To x plus one。X minus1。

And X andverse。This is sort of an interesting one， which gives you a three regular expander。😊。

There are other ones which we can talk about later on。Okay。These are expanders。In fact。

 I'm going to use reuse this part of the board， I'll need this part。知道。

People happy with these sort of little calculations out here。I'm going。Well be interested in。

Different notions of expansion。So here's a different notion of expansion。

 here's the spectral notion of expansion。Okay。So。I'm going to look at。Let me just make sure。

I want to look at the following spectrum notion， remember。

Lambda1 of the adjacentdjaency matrix was D， we said that this was the case。

Now I'm going to look at Lambda2。Of the adjacency matrix。嗯。And I'm going to define the spectral gap。

If v equal to is a definition， this is lambda 1。Mine is lambda 2。多文理人。哎呀。

1 minus lambda 2 over lambda1。没事。😊，This is a gap between the first and the second angle you remember。

 I said。If the graph is connected， then this is a strict inequality。😊。

So the spectral gap is strictly positive。嗯。G is a。Epsilon。Spectral expander。

This is their definition again。If the spectral gap。这这个真 I不知道。So this is trying to say， look。

The gap out here was captured connectivity。Just strict non zero net captures connectivity。

How big it is captures how expanding it is。Okay。And。So these are two notions of expansion。

 this is a combinatorial notion of expansion， this is a spectral notion of expansion in theorem。😊。

Due to Jeff Cheger。换色。呃。Functional analyst。嗯。Sigger says。Seager says what？Ceeer says。Age of。

The graph G。Is at more something and at least something。And this one is going to be one half。

Of1 minus lamb at two over。两 one。This is the gap， remember。Spectrum gap。

And this is at most square root of two。I one man family。Remember， these numbers。Are between。

0 and one。我 minus。Yeah。So square root of this quantity。

I as long as you know this number is between 0 and 1。

 the square root is actually bigger than the number itself。

There is a slight corner case where Lada 2 could be negative。But I think even in that case。

 things work hard。Okay， so this is jger inequalityality。😊。

Gigers inequality is saying basically both these definitions similar to each other。😊，Quallitatively。

 if not quantitatively。哎。Teaers inequality is a useful。😊。

Thing to keep in mind because it says you can move between these two definitions。冒着你。😡。

This is the EV。Part of Tea inequality， this is the difficult part。😊。

The difficult part is not too difficult， but I'm not going to do it today。😊。

Let me show you the easy part， it's easy enough and let's just do it。We good so far。Before we do it。

 let me just give you， let me tell you that triggers inequality as such cannot be improved。😡。

Both these inequalities are up to within constant state。So， for the example。Take a cycle on atices。

What is its conductance？How would you sort of minimize the？

How would you figure out the conductance of this？Edges， but a lot of what he see。😊。

Two edges crossing it and then about n over two ver is on one side。

 so this is so h of CNn is theta 1 over n。😊，But actually， if you do some of the work。

 then the spectral gap。😊，Is theta 1 over n squared？In this case。Showing that this is tight。

Square root of one over n squared is like1 over n， so this inequality is tight。😊。

If you take the complete graph， you'll see that this inequality is that。😊。

So basically on different graph。😊，These two quantities that this guy can oscillate between this and this。

If there's something you don't like。That's okay。You can look at higher order ch inequalities which have been developed in the past few years。

😊，Which actually allow you to give much better。Bos。Much tighter bounds。Okay。啊。

People use this to do image segmentation， for instance。

Or at least they use spectral methods to do event segmentation and to analyze it。

 you would use something like chi。😊，对。Oh， so complete graph， I think， complete graph。Edge。

Is approximately equal to the spectral gap。So this is， you know。

 both these things need to be checked， but I'm just。Fair enough。So far so good。这个。这本。

So here' is the issue right so if you are looking at just the conductance in the middle。😊。

Then the conductance could be anywhere between the spectral gap and the square root of the spectral gap。

So suppose I want to say that I want。A quantity。Which is。Within constant factors。

 a combinatorial quantity。Or you know， how do I give a tighter bound？嗯。Okay。

 so what it uses it gives you an inequality between lambda 1 and 2， but it says if lambda k。

 there is a gap between lambda k and lambda k plus 1。😊，Then Lambda 1。

 then then this kind of inequality is much tighter。Yeah。

So what I said was if theres a gap between Lada 1 and Lambda 2。

That's what I'm looking at out there right so it's saying if there's a spectral gap between lambda k and lambda k plus1。

😊，No， for some k。Then you can give a tidal bound out there。

Where the where the tightness now depends on this K。Make。やらまし番も完セ。Some people do。Right now I don't。

So I'm happy with knowing that these two things are at least morally similar to India。Okay。对。

Why do I care about expansion？So let's let's come back to why do I care about expansion why are we asking this question right I told you I'll teach you about high dimensional expanders and here I am talking about you know some definitions right so let me let me try to bring it back。

😊，Okay， so give a graph。I can do a random walk another。And here is my graph。Given a vertex。

 it has five neighbors。😊，I pick one of its neighbors uniformly at randomum and go to it。

It's a five regular graph I'm picking one of its neighbors and going to it。😊。

So I'm doing this transition。And now I'm saying， let us look at the so I pick a verortex。Any vertex。

 I start walking from there。I pick a random neighbor， I pick a random neighbor。

 I pick a random neighbor， I keep walking。So I can say I can talk about what is the probability at times step t plus 1 of being a vertexb。

This is equal to。😡，The probability of being at time T at some vertex u。Times。

If there is an edge from U to V。😡，Then I'll go with probability1 over d。Right。对。And this。

 I can say this is you over all lower of the graph。😊，So this I can rewrite as saying， let me look at。

😊，D inverse D inverse is just， you know， D is just a matrix。 It's a diagonal matrix with。These。

This is just B times the identity。D inverse times a times B。I'm just re this thing。So。

 basically I am applying this operator again and again。

 so basically I know whatever this evaluated at the V location so basically I am saying PTV。😊。

Is equal to B inverse a。Times D。电我。诶。😊，And the inverse in this case is simple。

 so I can just rewrite this， so let me just define a bar。😊，To be a1 over d times。え。

I'm just scaling things down't me。I'm sorry。G is Dreg for the almost the entire lecture G will be Dregular。

😊，Most of this will extend to non deregular， but Im not worried about that。And it's。

Eigenvectors will become lambda1 bar， which is equal to 1， and when lambda 2 bar lambda 3 bar， etc。

Okay。😊，Its just a rescaling， so the eigenvectors remain the same and I have an eigen basis I have F1。

 F2， F3。😊，Fn。The eigenvectors remain the same I'm writing them as thes because there are too many vs floating around。

😊，嗯。And I even know what F1 is， the top eigenvector is 1 divided by square root of n。

The all one vector divided square root of， it's a unit vector， it's a eigen basis， right。😊，Good。

So this I can just rewrite。As a bo。With a TF power。Thanks please。ok。😊，Good。This is Pete。Now。

 one good thing with having an eigenbas is it's a basis of all of space right so I can start writing。

😊，Be not。Enter in this basis。So。Like。They not。Be equal to sum C。F I。I went from one to f。

CIs are scalrs， Fs are vectors， I've just written P n in these places。😊，真。白 enough。😊，So this guy。

Is just a bar to the T。Time summation CFI。But I know exactly what these things are right so this is this is linear。

 so this is sumation CI。😊，Times I'm hitting F by a bar T times， so I should get back。

Lambda I bar with the T。F I。咩。So then let me rewrite this as saying C1。Lambda 1 bar is one。😡，So one。

 you know that to the T doesn't matter C1 F1 and F1 is。That。Plus。Sumation CI。

Lamb the eye bar to the P。And I， by being at least two。Okay。😊，As T tends to infinity。

 these lambda i bars are strictly less than one。Let's say the graph is not bipartite。

 this was one thing I should have assumed G is not bipartite。😊。

There a problem with bipartite mask a it， for now just say G is not bipartite。😊。

So each of these Lambda i bars。A strictly bounded away from one。

Because the graph will the only way in which you would get negative one out there would be if it's bipartite。

 it's not bipartite and it's connected。😊，So each of these things。I'm going to work with zero。

As T goes to infinitefin。Because this Ladaai bar。Is bounded between one and negative one。Open。

Because it's going to go too far。So this whole thing is going to become C1。

Times the one vector divideded by square root1。诶。😊，What is this beast， I don't know what c1 is。

But actually， I know what sea1 is。Why do I know what C1 is？Good。So T0。

 I just chose the starting point according to some distribution， right？😡。

It could have been you know just my favorite vertex。

 it could have been my favorite three vertifes uniform over them， whatever。😡，I don't care p n。

 so let us take the inner product of p n。With the function， with the eigen function， eigenveal F1。

But this， I know exactly what it is。😊，It's P0 the one vector divided by square root。Right。

P not as a distribution， a probability distribution。

What happens if you take a probability distribution times the all one vector？You get one。Right。

But this thing。It's a basis， right？P not， I was writing it in this basis。

 where did I write in this basis？I wrote in these spaces， right？If I multiply it by F1。

 what do I get back， I get back unit vector， its a basis。😊，Would this is unique to see one。

C1 is1 over square root n， so this just becomes equal to the old one vector divided by n n。

That's the uniform distribution。The random walk converges to the uniform distribution。Not surprising。

 but we just showed it。One more thing to check。You know， here I just said， oh。

 this converges to zero。😊，Now， if each of these lambda Is was smaller than 1 minus g for some G。😡。

G for spectral gap， remember？Then these quantities are going like 1 minus g to the t。😡。

They are quickly going to zero。The larger the gap， the quicker lift thing goes to there。

And we can make this precise。Maybe we will make this precise， but let's not worry about that。😊。

So what is this saying， this is saying if I gave you a graph and I did a random walk on it。

 I'll converge to the uniform distribution。😊，What's my graph， my graph was any fixed graph。

So let me define interesting graphs。Actually。So here's the graph I want to understand。

My graph is huge， it has some n vertices。And here is what I end up doing。It's an n vertex graph。😊。

Each of these vertices of this graph correspond to a spanning tree。😊，Of some underlying graph。

 So there is some graph。Let's call it E。On little invertices。I'm considering this huge graph。

 which has exponentially many verif。😊，This has n vertices n is。Something like exponential。

In little n， this is the spanning tree of this graph， this is another spanning tree of this graph。

 this is another spanning tree， this is another spanning tree and so on so forth。😊。

I have a Bazillion spanning tree the。I can go from one spanning tree to the other if there is one edge I can add and one edge I can remove。

😊，I have defined a neighborhood structure。I want to do a random of walk on a graph。

That just corresponds to adding an edge， removing an edge。

I can implement a random of work on that graph。I want to get to the uniform distribution。

I want to sample uniformly random spanning tree of this graph， that's what I'm trying to do。

This is saying， if you take。Enough steps you'll converge to the uniform distribution。

How many steps it depends on the spectral gap of that beast。

I need to understand the spectral gap of time piece。That's the's that's where it comes down。

 you know what is。Is the spectral gap。Of this particular graph。Should we understand it spectrally。

 should we understand it combinatorally？The answer is yes， because Chiger says it's the same answer。

😊，冒着里。😡，So that's where we we are going basically you don't want you're not interested in spanning trees well。

 you know the physicists who are interested in sampling。😊，lorings of the graphs。

 they are interested in span sampling independent sets of graphs。

 they' are interested in span in sampling matchings of graphs。All these problems are sharply hard。

 we don't know how to do them exactly。Sppanning trees， we do know how to do exactly。

So then how do we proceed， well， we use this Markov chain method。😊，No。If there are companies where。啊。

If they have constant， they're tight， exactly， exactly。😊，你好。In research search of application。

We I guess you're trying to argue that if it makes past anyways than any of them doesn't。

In some cases， I mean， it will on a case by case basis。And very often we'll be interested yeah。

 so it's sort of completely case by case basis。😊，And also our techniques might be not strong enough to show a constant spectral gap。

 even though it exists， we might say， oh the gap is only one over log n or something。

 even though the gap is constant。😊，Like if you have like a linear and a sp root different。

And and find the。Exductive。Then just do it twice， and you won screw。那个。Don't know what you mean。好。

Okay， let's discuss that when we take a tu and break。😊，Are we good so far？

This is what we want to understand。😊，And this is what we' will do you know。

 in the next lecture we will basically try to understand the spectral gap of this guy。😊，But for that。

 we'll need a little more technology right now we don't have that technology。

Yeah good so then the real question comes， how do you sample from this， how do you take a walk？😊。

I can define the graph， but I don't know how to take walks in this。😊，So there's this tension。担。

And there are many different dynamics I just give you one dynamic， add edge， remove edge。😡。

People are often interested in， oh， I'm going to do these large scale steps。😊。

There's something called random clusters， there's something called Swanen Wang。

When we and W they're getting confused again， various things can be done。😊，The real problem comes。

 then how do you understand this？How do you implement these？Totally excellent。Other questions。

So far gl。Good okay， this is what we want to do Min thing let's let's just let me define an object that I'm interested in。

 So this will call the total variation distance so if。😊，You know， of all the definitions。

 variation distance。So this is often written at d subtv between two probability distributions I'll call this p and q p and q are two probability distributions the total variation distance between them oh so let p and q。

The probability distributions the sample over the same sample space。Overall， omega。

So this is the max。Over any subset of mega。Of the probability that P assigns to s minus the probability that Q assigns to S。

Actually， I don't even need absolute value。对。What is the worst event？😡，嗯。For this quantity。

And if you stare at it。You'll realize that this quantity。So I always keep this picture in mind。

Let me get two different colors。点能知。This is P。This is Q。

I want to figure out an event which maximizes Pf minus Qs。So what should I do？哎哦。The sample spaces。

This's。So what should I do？I can look at this portion where P is bigger than  Q。

And I can look at this portion where be bigger than Q。And this is some subset of the sample space。

And in fact， this really does maximize。😊，Gap。Out here because I've captured all the space where P bigger went you。

😊，And if I think about this， this is really half the L1 distance between P and Q。

So the total variation distance， if you don't want to remember more definitions is' half the L1 distance。

😊，滚。We could。So I want to， you know， so what is the spectral gap because really the question I want to ask。

😊，This is the question that people ask and this approach is known as Markov Che and Monte Carlo。😊。

Markov chain Monte Carlo， this is the sort of main question。😊，呃 our。Large。A value of t。Such that。

Pt okay， the distance in total variation。Between PT and the uniform distribution。

Is less than some delta。This is what I'm interested in。

Very often people ask you for other notions of distances between distributions scale。😊。

Here's another one common one that you've seen at some point to cool back liberaller divergence。

 but let's stick with total variation。How long do I need to run the markov chain before the total variation becomes less in delta？

So let's just do quickly this thing。So the total variation。Between PT。And the uniform distribution。

Israeli。One half。Of Pt minus the uniform distribution。Ll1 norm。

With the L1 norm is at most square root n。Because this is a space of size square root 1。Timemes。

They are two norm。Okay。😊，Which is。We already know what PT minus all once is， it's this sum。

Is equal to。Square root n。Times the square root1 over two。Times this sumation。是。Hi。Lambda， I bar。F I。

 this is to the T。than成东航。Okay。And now I want to say。Let us say that this spectral gap。Is。G。射。

Spectral， oh， so I don't。Gap。I at least epsilon that。It's a spectral expander。

Then this guy is smaller than one minus epsilon。Because it's a spectral gap， right？

So this becomes square root。Times 1 minus epsilon to the T。Times， whatever。Some garbage。And this is。

 you know， is at most。This thing is some quantity， which is at most one or something like that。

So really I'm interested in this and if I make this at most delta。😊。

If the number of time steps is at least log off。And over hapsilon。And over。Delta overlaps。

This is just algebra， the important thing to note is that if I want the total variation distance to be small。

😊，How many steps do I need to run， I need to run log n steps。Over Epsilon， this is a spectral gap。

So I would like my spectral gap to be good。So that my number of steps is more。当。

But my Lambda 1 is in this case， where actually， where did I lose lambmbda 1 somewhere？

Lambda 1 was one in lambmbda 1 bar is one in my case， so I don't need to worry about it。对。

Important thing is that the number of steps I need to run is log in the size of the graph。😊。

So if the graph is exponential， that's fine still。😊，Login exponential is polynom。

But I really want my spectral gap， so this remember is the spectral gap。

I would like my gap to be really cool。This is awesome。Loarithmic in graph size。By the way。

 this should be surprising to you。I'm going to run， I have this massive graph。

 I'm going to run for a number of steps which is only logarithmic in the graph size。😊。

And I'm saying I'm nearly uniform。So it better be the case that I can actually reach every vertex。😊。

En log many steps。For my graph to be you know， for this to be even a valid statement。

But this is because I have assumed its an expander， right？What's an expander。

 an expander says start off with a single verortex。😊，I'm going to see a lot of edges。

 so I'm going to see a lot of what。Now I have more vertical fields， take another step。

 each time I'm increasing by a factor of onelyhepsilon or something。Quickly， I'll see brand。

En log many steps。你到的还有。This bound is tied up to constants。

The important thing to remember is that if I want。😊。

Something to mix rapidly this is did I write somewhere okay so maybe I'll move this up so this phenomenon is called rapid mixing。

Papid mixing of Markov chains。So I've mentioned this only for the uniform distribution over like just random walk on a graph。

 but you can extend this to Mark of chain the rich theory you' just single beginning so if。

Line and walk。As spectrum。Yeah。At least steps along。And。As let's say N states just to make it clear。

Then。After。诶。E， which is。哦。Law of capital N over Delta over Epsilon。We are。呃。Delta close。

To stationery。呃。And Delta close。In total variation distance。嗯。

So the spectral gap is what we care about。Whether it's an expanded or not。And in the late 90s， no no。

 in the early 90s， late 80s。😊，A group of people showed that several chains that people were using。

To for rapid mixing so this is called rapid mixing， this is a standard term right now。

And then people used it to show。That her chain on matchings was rapidly mixing in particular bipartite matchings。

Then they showed various other chains and amongst the people who did this were Prasatatetali。

 who's the head of the math department out here。And also my advisor， I waste Sinclair。

 whose PhD thesis was on this kind of stuff。嗯。So it's you know a very beautiful area。

 but very simple ideas you know once you have the right algebraic machinery what did we do all we did was just wrote the damn thing and the eigenbas。

😊，And did the most elementary of calculations。And boom， we have the answer。哎。You can do a lot more。

 but I'm not doing it today。Yeah。Good。So。This is what we are trying to do。How are we doing on time？哦。

没始。Okay。So。诶。You can go in in one of two different ways。

Maybe for 15 minutes I'll talk a little bit about。诶。

It sort of a slightly different direction and then we'll come back to this so here's a here's a slightly different direction that I'll talk about since we were talking about why do we care about expanders and。

😊，This。It's not clear that expanders， all of us have to。嗯。Deal with expanders and Markov chains。

 here's a completely different setup where Markov chains where expanders come up。😊。

So let me tell you about a slightly different problem， it's a problem in coding。Encoding theory。诶。

So what's coding theory？呃。In codingding theory， I'm interested in sending messages right I'm interested in taking you know a K bit。

😊，Message。I want to encode it as an end bit。Courd word。I send it across a noisy channel。

And I want to make sure that I get， you know， maybe a corrupted。Word。Then I want to decode。

This is encode code。对。Now want to decode。And what do I want to say。

 I want to get back the original message。If。Fewer than。See corruptions。

This is the basic idea of coding。😊，The three parameters that we care about。The parameters。

 the first one is。Here。The number of bits I'm encoding。And the length of the encode。And。

How many corruptions can I handle？And the way I always think about this is that， oh。

 this is the space of all code words。😊，And if the minimum distance between any two code words is at least to c。

Then if I have only three corruptions。The closest code word decoding will give me back the correct answer。

So I want the minimum distance。To be at least2c。I'll call the minimum distance， you know， whatever。

 this is the minimum distance。So there are three parameters we care about a bunch of other parameters if you really want to。

It's called N。嘅。And I'll call this main distance。This is how all code wordss are you know coding schemes are written。

 you say， oh， it's an NKD code。😊，You know， board it。

How many bits are being encoded into how many bits whats the minimum distance these need not be bits you could talk about a larger alphabet and then in which case you would put the alphabet size I am not worried about that。

😊，Because I'm giving you again somewhat quick impressionistic view of what's happened。对。Good。

Often you'll say N。Okay， so。C divided by n is called the rate of the code。Menest。

Over n is called the relative distance。It'sJust a relative distance， that's just a definition。

So what I could say is that suppose I will parameterize the rate by R and the minimum the relative distance by delta so then this is just n。

😊，Rn， delta n， I've just here re parameterametric is it not important。

If both are in Dlta or constant， this is known an asymptically good code。😊。

This is the gold standard in some sense。We want to build asymptotically good courts。Okay。

How do you get asymptically good quotes， where it's kind of complicated。😊，啊 so。

People have been looking at this， but you know this idea has been around for a long time and here was a simple idea due to a researcher called tanner。

😊，They said the following。Let us take a graph。We'll call it an expander。讲。I regular expanded。

 let's say。I'm going to build an asymptically good code on five bits。😊，诶。

Now this graph has some number of vertices， this is a poor choice of notation。😊，Yeah。

 this has capital invertices。😊，And it's little and regular。Okay。😊，Here's what I'm going to do。

I'm going to say。A word oh， so I'm going to write a bit on every edge of this graph。😡，Okay。

 one bit for every edge， they changes。So the size of the code words， the length of the code words。

Is the number of edges of this graph， which is inver fees。😊，Degree， little N。

But you divide by  two right because I'm double counting。Okay。😊，Good。

What are valid code words of this code？Here is the valid code word of the code。

 so suppose I say you know I wrote 10，110。😊，There is some particular every verortex looks around it。

 it sees little n edges。😊，It has some ordering on them。So it reads n bits， five bits。

If this belongs to this base code， it says I'm happy。A word is in this。In this big code。

 if every vertex is happy。Does this make sense？嗯我大人发。So there's n vertices I've taken a graph。😊。

This is an expander on capital NticC。看。It doesn't matter Cha N is some number。

All I am telling you is that theres。The degree of each of these guys let's say fi regular。😊。

There's a five regular graph。I also have。A good code on five bits。Okay。😊。

I'm now going to define code words。Onです。呃。On so many bits。

There's one bit for every edge of this graph。😊，A labeling of the edges of this graph with bits。😊。

Is a valid code word。If。The five bits around vertex 1。Belong to this belong to this code。

The five bits along vertex2 belong to this code and so on。Every vertex looks around itself。

And sees the five bits around it and if it sees a code word it says， okay。

 I' am happy if all verv are happy， that is a code word。😊，Okay。Does this make sense。

 does the construction even make sense？I can do a little example if it happens。

The vertices and edges represent it' is just a mechanism for taking a ch word on five bits or taking a chor on five bits。

 which is a tiny little code。😊，And I'm going to get a code on a large number of bits。😊。

This is just like an abstraction。Maybe I'm confusing you guys， so ask another question。

Maybe I should say something。で三。So is here is an example。Let's do the following thing。Let's。

So let's take a grid， let's make my life easy。And it's actually a tarus。

 but let's not worry about the boundaries they' are all wrapping around things like that。😊，Okay。😊。

Valid code words are going to be so there' is an underlying code。

Where every valid code word has even parity。😊，So the code words are on four bits。

So it's the code words are zero， all four，0，0，1，1，0，1，1，0， etc。😊，These are the court words。

Notice that the distance between any two chvers is2。喂。😊，It's not a very good code。

 but it's a valid code。😊，I want to define， I want to say given this base code。😡。

I'm going to produce a code which is not just on four bricks， but large number of plates。😡，诶。

What are the code so in order to give you a code， I have to tell you what the code words are。😊。

So what are the code words？Here is the code will。Which places zero on every edge of this graph。😡，喂。

This vertex looks around itself and says， oh， I see four zeros around me， Im happy。😊。

This guy says I see zeros around me， I am happy。Every vertex。When it sees four bits around it。

 those four bits belong to this school。Okay， so this is one code word。😊，Here is another code word。

And now this starts to get interesting。😊，So okay， here is another labeling of the edges I've just changed these two bits out here。

😊，Is this a code word？😊，This one will be unhappy。So in order to make this a code word。

 I need to have at least one more one sitting out here。Is this a code word？No。

 the bottom one is unhappy， maybe I need another one out here。Is this a ch word？Yes。

 this is a court word。But notice。😮，That because I created a little perturbation out here。😊。

In order to fix this problem， I had to create another perturbration somewhere else。😊。

Another perturbation somewhere else。A small perturbation in the graph caused a larger perturbation。😊。

Now， if there were no short cycles in the graph。I would have had to create a lot of once。😡。

Does this kind of make sense？That's the whole idea。

That you can't just change one bit of a code word and get another code word or two bits。

 you have to change four bits。In general， you might have to change a large number of bits。😊。

And that's really the essence of coding theory。😊，That if you take a code word and you just perturb it a little bit。

 no no， that's not valid， I'll be able to decode it。😊，You'll have to put up a lot。切。

This is not an expander。That was the problem What happens in an expander is if you perturb a little bit。

😊，There are a lot of boundary edges。So people will complain， I mean。

 I'm being vague out here I can make it precise， but we won't be able to make it precise。😊。

So if you make a small change， you'll have to make a large change。😊。

You started with a code on just four bits now you have a code on any end。Take any four regular graph。

Of arbitrary size。I have given you a recipe to create codes of that length。You know。

 there are n word fees on this。And it's for regular， then there are two energies。Then on any 2N edge。

 you， any four regular n vertex graph， you can lift that code and get another code。😊。

And my claim is if that graph happens to be an expander， then this code is very good。😊，Okay。😊，This。

 by the way， is called a。😊，What didWhat were we doing we were doing parity checks。

 every verortex is doing parity checks。😊，How do you decode？You just do you know， each verortex says。

 oh， I see a problem around me， let me fix it。😡，This creates a problem somewhere else you will fix it and so on and so forth message passing algorithm。

😊，These things are known as。Low density parity check codes。

A few years back people were using technology called tornado codes， they were using turbocodes。

 all these are based on the idea of load em parity check codes。😊，And the main idea。

 main underlying object behind it is to， one is you need a base code。This was a crappy base code。

 it had minimum distance too。It can detect one error， correct zero errors， sorry guys。

But you can come up with better records。Especially small ones， I need it only on4 bit， five bit。

 six bits， you can do bed。And then you can lift the cord。And this idea of lifting very powerful。

AVery simple as well。😊，应该。那。对。儿童方程。Eruption， so I can I can tell you what parameters you you get if you start off with。

嗯嗯。N， Rn， Dlta， N code。Then you will end up with， let's say whatever。Capital n little n over two。

 Okay， let me just call it M。M is capital n， little n over 2。Your new code is a length M。啊。好了。

What's that？It's small and yeah， so this was a N vortex graph， little n regular。😊。

So then you'll get M length thanks， and I will have to look up exactly what the。Good人。2 r minus1。M。

So the rate。Became worse， so you better have a half rate and this is Delta deelta minus lambda delta minus epsilon。

Where this epsilon is the expansion parameter。This is what。So everything， you know。

 the parameters are what they are， like can you know， we can go into details， perhaps。😊。

I'm not worrying too much about it。With the important idea of there。

That if you have an error somewhere， the error propagates。You can't just have a small set of theirs。

Good。嗯。So that's what I wanted to say about expanders。啊。

I had and grand plan said I would tell you guys the basics of high dimensional expanders。

 but maybe in the three minutes remaining at least I'll give you。😊。

Two definitions that are very simple。So what's a high dimension experiment？I dimensional expander。

 I love the name， by the way it's a great name， it sounds like some kind of explosive device。😊，啊。

Okay。So the first definition。Is that of。It's impial complex， now forget it。

 it's called a downward closed set system。😊，Okay， so a high dimensional expander consists of an underlying set of elements。

 think of these vertices。😊，And a collection of sets。Subsets of this， it's downward closed so if。

S belongs to this family and T is the subset of S， then T also belongs to the family。This。

 my friends， is what is called a sial complex。😊，In fact。

 the first time I heard the definition simpleimial complex。

 somebody said what is a downward close set system， why it's just a sial complex？😊。

I love the fact that you know just just means different things to different people right for people who know it simple or complex is a simple idea for me downward close that system is the right idea so this is。

😊，えけ a。A simple，cyclic。I always feel like a faker when I'm writing this thing。O。

The sets of this thing are called slicies。😊，哦。Or faces。

No yeah I mean it's just simple I then it's it's like a so so here is here is a simpleial complex so often you know these simpleial complex are written very nicely。

 so here is。😊，It is a。You write down the empty set， the empty set is part of this beast， right？

And there are three four elements， A， B， C， and D。So a belongs to。B。是。And now this edge， A B。

Belongs to it， A C belongs to it。啊。BC belongs to it， C belongs to it。And maybe。

ABC also belongs to the simplicity complex。It's just some collection of sales，man。Download list。

if you want to be fancy or not fancy， you know it is illuminating you can write down these links these edges out here which is saying who is the subset of home？

😊，The Haa diagram， I think I remember right。What's that？😊，Okay， good。We all know mes。

 these are splicial complexes， but they have one extra property， they have the exchange property。😊。

They have one more extra property， which is。😊，All maxim sets。😡，Have the same cardinity。Here。

 CD is a maxim mu set。😊，Which doesn't have the same cardinality， in fact。

 the ranked property will take care of that。Yeah。So anyways， mattris。

A special class of simple complex。😊，对。Theres a download load set system， okay， good。So far suburb。

What have I defined nothing？Oh， we are out of time， what a surprise。啊 good。

A simpleimation complex is called pure。😊，If all。Maxxiimal sets， inclusion by maximal sets have。

Same cardinality。This is not this is not one， but now I have added one BCD。You know， BCCD。

Or maybe I'll have to add in B now。Where name。This is a pure simpl complex， okay？😊，对。By the way。

 this sial complex， if you ignore the fact that this was a simplex and this was a simplex。😊。

It's just a graph as well。In particular， if you ignore everything above the first two levels。

 this is just a graph with a bunch of edges and a bunch of vertices。😊，Okay。😊。

This graph has an expansion。Keep this in mind。Now， for every vertex， you can look at the up。😊。

Set of this thing you can see what are the elements what what is this whole beast that contains a。

You A is contained in A B and A C， in ABC。です。Peace is another s complex。Was's that。😊，Oh dude。

 getting ahead of me。 No， no， no， this this is just some simple thing， right， I mean。

 this is like a four。Like a very simple， simple little complex。 So if you think about it a。😊。

Contains， you know， A， B， A， AB C。喂。😊，So what's the the so this is called the link of a。

It's like a little portion of this s complex above a certain set。😊，That itself is a s complex。😊。

And you can talk about its expansion here， the ver see at this and the edges at this。😊，So， this。对。我。

It should be。就t在病。Okay， good， good， good， good， good so， so。

 so what I should do is once I look at this， so this is called the link。😊，Ofて。

It actually consists of， so now this will be the empty set。This will be B。

 so I'll remove a from all of them。😡，I'll call the C。And this will just contain Bes。Oh sorry。

Yes行 yeah。B， C， B。D the from each of these guys。This is the link of it。So for every set。😊。

Take everything above it and drop that site from all those guys。

That's another simple complex and now you just have to yeah。😊。

That has its own graph that has an expansion。😊，If all these guys are expanding。

This is called high dimensional expander。Why do we care about this because right now there's a bunch of results that people are proving things？

And they're proving things just by almost elementary properties。

 just like we were using elementary property， the elementary properties of high dimension expanders。

 it's like you know， these are it themselves non。😊，Trivial properties。

So next time I'll define this again。😊，But really， the whole idea is， I'll take a。😊，Bast and HDX。

 the simple little complex。And look at the various graphs。没有了。

look at the graph consisting of vertics and edges and then for every little guy out here I'll look at it upset and Ill look at the vertics and edges。

😊，And I'll say， well， and if all of those are expanders。

 then this is called a high dimensional expander。😊，In particular meteors。

 meteors form a high dimensionional well， meteorides formal。😊，Beast。

Is the beast a high dimensional expander is it an expander we don't know。

 but next time we will see it is indeed。😊，And so rhino walks and these things mix quickly。Yeah。

 let me stop。