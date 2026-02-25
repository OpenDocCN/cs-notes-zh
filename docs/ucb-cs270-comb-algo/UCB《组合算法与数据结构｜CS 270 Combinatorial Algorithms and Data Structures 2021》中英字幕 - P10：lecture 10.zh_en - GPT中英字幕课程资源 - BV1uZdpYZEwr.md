# UCB《组合算法与数据结构｜CS 270 Combinatorial Algorithms and Data Structures 2021》中英字幕 - P10：lecture 10.zh_en - GPT中英字幕课程资源 - BV1uZdpYZEwr

![](img/bd5d76f3366efa5e940866ef3a095826_0.png)

Welcome back。Today， we。Our plan will be the following， so we will start with。

We'll wrap up the proof of oblivious subspace em。Which we started last time。

 there's a one small piece left there。 we'll finish that up， and then we will。Look at a particular。

You could call it an application of ob of space embedding matrices or just。

Another version of dimension reduction。嗯。It's。Wter called comp。

So just to recall where we were with the proof of obli subspace em。

 let me just recall the theorem that we were proving so the theorem that we were proving is the following。

So we have a random Gaussian matrix， which is P by n and if you pick at least this many rows。

Then for every subspace of dimension D。You preserve all distances。

 the linear transmission preserves all the distances within the subspace。 so in particular for every。

Subspace of dimension D with probability 1 minus delta。For every vector in the subspace。

 the length of the vector is。Within one plus or minus epsilon of its true length。

GU is is the length of the transformed vector is after dimension reduction and。

That's within one plus minuspsilon factor of the whole space。

So we saw how we could prove that for any given vector or any given inner a product。

It's you can you preserve the length with good probability by something analog to a shut enough bound。

 we proved it last time and then we looked at the situation where we had to preserve all distance between n points so that was n squared pairs and then you know we could just do union bound over every pair and now in this statement we have to do a union bound over every vector on the subspace。

So for every vector in the subspace you need to have this。

 so there are infinitely many vectors and the way to get around this to actually prove a union bound。

Or here is to pick a net so a grid I said a grid last time。

 buts it's usually the standard technology is a net so a gamma net。嗯。Yeah。

So you have the this is the unit ball。In R to the D， a gamma net is just a bunch of points。

Such that if I give you any other point x。There's at least one of these points in this net within a distance gamma。

So a gamma net is a set of points， that for every point in the ball。

 there exists some point in the net， which is close by。

So you can think of a grid essentially and you know。

 we saw that you know you can pick a gamma net of size roughly exponential in the dimension。

And think of gamma as some small constant001 I mean egg that's a reasonable thing。

 so let's just think of gamma as some small constant so really you can pick the gamma net with exponential many points in it。

Okay that's one thing and the second observation is that you know。

 because we have picked a dimension reduction， the parameters of dimension reduction to be sufficiently large。

 the t， the value of t to be really large， you can actually do a union bound over every pair of points in the net。

You can assume that you preserve the distance or the inner product。

 let's say between every pair of points in the net。With error at a plus or minus eps silenton。

 so that's what we are saying here。So for every pair of coins x and y in the net the inner product is preserved up to epsilon okay so so far it's good so we have that our linear transmission is nice on the net now we need to prove that the linear transmission is actually nice on the entire ball which is a continuous object。

And we'll do that now。H。And。So here's a claim about。The ball。If you give me any point in the ball。

 which is not in the net， right any point in the ball， then you can actually write X。

As a linear combination of points in the net。Okay， this is not surprising， Of course。

 if if you had a basis， you could always do it， but the key point is that。Well。

 there are what whatever number of points you have the key point is that these coefficients their sum is smaller they decay。

 for example， so where。The cardinality of alpha I is like 1 over2 to the I is smaller than 1 over2 to the I。

Here and。So let's see why this is true。It's a very simple proof。 just recurs you do the following。

 So okay， I want to write X as a linear combination of these。 Well， the natural thing is okay。

 let me call。For notational reasons， I'll call x1 equal to x。Okay， I call x to be x1。 Okay。

 now what's the most obvious thing to do you pick you know y1。To be the point closest to X1。

Cllosest point。In the net。2 x1。Okay， just photo。So it makes sense that you would want to， you know。

If you're trying to write x as a combination of points in the net。

 you'd want to use the closest point first， So you just let's do that。

 So let's write x1 is equal to you know y1 plus x1 minus y1。Right just this。And then， let's write X。

Okay， so this is good right， so what do we have here？We have a point in the net。Okay。

 and then we have some residual residual point， this residual vector。What do we know about it。

 well its length is ut most gamma。Thiss a short vector。ok。

That's because because of the fact that we have a gamma net， if I pick the closest point。

 the distance to it will be u most commona。Right， so。You，So I mean。

 theys just recursively express the residual also。The serial is also you know after normalization。

 it's a point in the ball， so let's write that also as a linear combination of points in the net and repeat。

So I'm just going to first normalize it， so I just say。This is norm x1 minus y1。

Times the unit vector， x1 minus y1 by no x1 minus y1。Okay， let's just normalizing it。Okay， so now。

This residual vector， if I call this x2。It's also a unit vector， x to his unit vector now。And。

So therefore I can do the same trick on x2， so let y2 be the closest point to x2。

Clsest point in the net to X。It is some point close to white， so just repeat and know say okay。

Y1 plus nor mix1 minus y1。Dmes。I'm going to write x2 as y2 plus x2 minus y。Right， so but， you know。

You get the picture I am just going。Again， make it unit vectorctor。什。Okay。就诶。Or to have a。

Y1 plus no max1 minus y 1 times y 2 plus。Whatever this thing is。

 normm x1 minus y1 times normm x2 minus y 2。Time if I call that unit vector， the residual left。

 let me call it x3。You that takes three。Okay。And you know， I can repeat this。

X3 I can again pick the closest point， subtract it write it so what you see is that like the look at the first coefficient here。

 this is atmost gamma because the distance from x1 to y1 is atmost gamma。Yeah， right。

 So alpha 1 is one。 Yes， Alpha1 is one。 Yeah， I should get one or two die minus1， I think。

Yeah alpha one is one you see that the second coefficient is at most gamma the third coefficient and gets two factors of gamma in it one factor here。

 another factor because it gets gamma squared anyway I I expand it out a factors which are like。

Like a geometric progression utmost upper bounded by geometric progression。Okay， they see that it's。

一。Yeah。Right， so that's I hope you can see it now as it's sort of。And and you know。

 basically inductively， you can write it as a。嗯。As a series where each coefficient alpha I is decay。

Actually， as I've written， you want and get a finite expansion， you'll keep getting。呵。

You get an infinite series for x， but that's fine。As long as it's good。

So you can're writing X as an infinite series with decaying coefficients in the net。Okay。

 so now that we have this， you know。we can。So now we can。

 you know we're ready to prove what we want to prove。

 what do we want to prove if you give me any point text in the ball。

I want to prove that the length of Gx。Any pointex。I want to prove the length of Gx is。

About right is the length of x plus or minus epsyilon So one thing I have done here is I'm I'm using the word ball when I actually mean the sphere。

Typically ball would mean would tend to imply a solid ball where the length of x is at most one。嗯。

But actually what I think in this theorem and maybe in the last class I've been using ball to mean in the sphere。

 so it's really the sphere so。O。But you know everything is scale in so if you preserve the length of every point on the every vector of length one。

 you also preserve the length of every vector of different length。

 just by a multiplicative factor you can write it down。Okay， so let's look at。

let's look at the length of this vector Gx。RightOkay， firstly， it's in a product of Gx with Gx。

Alright， and then by definition， you know， by our claim， we can write this as。

Some were i equal to 13 infinity， Al I Y I。Some are equal to 13 infinity alpha I IR。😔。

So this is just。Oh， I should， I should miss the G G times that。G times step。

And the sum here goes from one to infinitefinity just because of the way we wrote x as an infinite series。

 although you have only finitely many points in the net， the process generates an infinite expansion。

 of course is Ys will be not distinct in this expansion。

 but that doesn't matter for the proof ofvers。Okay， so what does this do well this sum or IJ。嗯。

Alpha I Al J， and then we get G， Y I， G Y J。几 just啊。

So the key point now is these two are points in the net。Okay。

 and we already saw that our linear transformation preserves inner products for points in the net so I can write this as。

什么来枝。Alpha I， Al J。系い。It's actually equal to Y I， Yj。

Because it preserves points in the net thinner product and then you know。

 some error plus or minus epsilon。Okay， that's。Okay， so that's good。 And now。We unwrap it， right。

 so like the first。The first term I can write it as someur I， Al I Y I。Some more J alpha j Y J。

That's the first step。嗯。So let's。One， the first term。

 and the second term is plus or minus the error term plus or minus epsilon。但 sir。basically。

 somewhere age。Alpha I alphaic。Okay， so's just。嗯。All right， so now you know what is the first term。

 well some or alpha I is x。This is just x in a perfect x。Okay，And really。

 the key point is the second term is what it's。Epsilon times the error term is something like this。

 some or5 hole squared。Okay， and。Main point is because alpha is are geometrically decreasing the sum ori alpha I is bounded。

 it's like some two or something， it's some constant some two， let's say it's two。

 so it's at most some order one。This thing is at most order one。

 So what you end up with is like an order epsilon error。Okay， that's the key。

So if you had Epsilon error on points of the net， you sort of get out Epsilon error on then every point in the space。

And so that's。That's basically。Okay， and I guess the key thing is that the。

If you essentially if you want to union bound over a continuous。Sp continuous region。

 a continuous set of objects， typically what you pay for is the volume or the log of the volume。

So the size of the net was exponential in D because the volume of a D dimensional ball is。

Exonent Lidy。That's the reason why this size of a grid is exponential indeed D。 And。

 the dimension that you pay for is log of the volume。 It's like log of the。Size of the net。

 So you get a。The you get a D here。D this D comes because you're union bounding against the exponential indeed different points of the net and this log1 over delta epsilon squared is just what you always get。

Okay， so that's say。你不是真的。Right， so。So。Yeah。So， so one thing I did was in this proof。

 I used the fact that the。Inner products between。Pace of points in the neck is preserved under this transmission。

 but。Essentially， there's a。Like this is also true just by what we saw earlier in terms of churn off bounds and so on。

 but even otherwise preserving lengths and preserving inner products are kind of very closely related so。

So。You you can， you can。Up to constant factors move between the two。不是。O。All right， so that's good。

Okay， so let's that's all I wanted to say about oblious subspace embeddings。

 so just to step back what we got here is that we got a transformation that preserves distance between all pairs of points in the subspace and we can use this to do linear regression or PCA or matrix multiplication many other things。

三？Much faster Basically if you have a matrix and what you care about is sort of the。

 let's say the column space of a。Or let's say the row space of a and you don't really care about the rows of a。

 but actually just the row space of a， like for instance， in linear regression。

Then you can apply this dimension reduction to reduce the number of rows from being。

Whatever it was to something that only depends on the dimension of the vectors。

So you can speed up a lot of different things using this technique。Okay， so。

What we'll see now is another。Sort of application of dimension reduction。So。嗯。Compressed sensing。So。

 you know， if I had to say it in one sentence。Like we saw dimension reduction for sets of points。

 we saw dimension reduction for subspaces， this is like dimension reduction for sparse vectors。Okay。

 but let me。Ievrate a bit more。So the I guess one thing that people observe in practice is that if you look at many signals that arrive arrive in。

Natural context， like images。Audio。嗯。They all are many many other settings。

 really usually the signals are sparse。In some basis。So for example。

 images you use JPECG compression and JPEG compression uses the fact that the reason JPEG compression works is because。

Image an image is not a random binary vector， but it is really in an appropriate basis。

 like if you took some Fourier transform or took some wavelet transform。

It's representable by a very sparse vector you don't need it so although your signal x。

It technicalechnically is an n dimensional vector。If you write it in an appropriate basis。

In an appropriate basis。Most of the coordinates are zero， it's a sparse vector。

 zero or close to zero。So。I guess I'll refer to define a vector axis。嗯。I say it's。Cisse pass。

If only K coordinates an 10。Only you know， or if less than K coordinates an answer。Okay。

 and of course in。In real life， you would not have。嗯。The case pass vector。

 but you would have something which is approximately case parts thered be some small set of coordinates which would be non zero and on the rest the norm of the rest would be very small like if I had to say had to define let's say。

嗯。You know， access， you know， epsilon， approximately。Case pass， if I had to define that， I'd say。あ。

You know， there is。If there exists some subset of coordinates。Like atmost care coordinates。

Such that outside that subset， the vector is basically zero。

So let's say if I take the norm of the remaining coordinates。

 it's at most epsilon times the norm of x。Okay， and if you could define any norm。

 you could define it one norm or two norm and so on。But。

So that's the idea of that's what we mean by SPA。There are a small number of coordinates that。

That have most of the mask。And in this lecture we'll only be talking about actually case perspectives just for simplicity。

 but whatever we say will extend to approximately case perspectives。Okay。

 so what what's the situation well you know images like JPG or audio and everything they have they are very sparse in some basis okay and that's nice。

 but then you know。It also suggests that there's some inefficiency in capturing the entire image。

And then compressing it。Right ideally， you would want to just。Just get the small number of。

Noze coordinates of x。You just want to measure it physically if you a camera that could directly just measure the non zero coordinates of x。

佢逼佢。Okay， and you could hope to do that right， you know。

 that's not the only reason it's difficult is you do not know a priori which coordinates of x will be non zero。

There are n coordinates of x in some basis， and you a prior do not know which coordinates will be zero therefore。

 you know you can't just go measure。嗯。Like x1 x to x3 they might most likely be zero right so you want to make very few measurements or have very few sensors in your camera or take very few images but still be able to recover the sparse vector fully okay and that's the idea behind compressed sensing。

So。嗯。做历食啊。😔，So compressensing。嗯。If you have some signal which is inherently sparse。You want to。b。

You know， use。Some much smaller than n measurements。嗯。So if you have to all the x is n dimensional。

 you want to use only like something like think of it as roughly K log n or something much smaller than n measurements in an upper and then use that only those measurements to recover the true x。

That you want to take advantage of the fact that X is bars。

And so we'll be dealing with in this lecture only about linear schemes。

 So in a linear compressensing scheme， this what happens。 So you have a。Measurement matrix。

So what's the idea of a measurement matrix you pick on。嗯。

T by n T by n matrix so what so what is the idea you know？You have x1 through xn。

Instead of measuring all the coordinates of x， you actually measure。Just the coordinates of Mx。

So what are the coordinates of Mx each coordinate of Mx is just a like you know。

 it's a linear combination of your original coordinates right there are T measurements in essentially。

で。And of course here I'm assuming that in your physical system you can actually realize like you should be able to measure a linear combination of coordinateex directly。

 otherwise there's no point right if you want to use this in a physical system you should have a camera that can actually measure M1 in a protex directly so measuring X1 through xN if you measure M1 in a protex m2 a m in a protex。

So。So let's assume for now， you know， that that's the case that you can actually。

Measure these directly directly these linear combinations and now your problem becomes given these things。

 you know that X is sparse。So you want to recover x， so your algorithmic problem becomes given Mx。

The color。Okay case pass。Ex。Given a Mexico to B， you want to recover。

 okay that's the algorithm equation。做。So we'll see how to do this。But you know。

Right the compressensing， the reason it's。嗯。Has had quite an impact is because。

There are applications in which you can actually。Pick and m。

Such that you know you can actually measure M1 dox empty dotex and actually use this entire scheme and the MRI is an application where this is。

I think it's already used in MRI scanning and so on。

 it drastically reduces the number of images or you need to take and things like that。So that's the。

SoAnd that's neat things quite neat you。But underlying that this is an algorithmic question the algorithm well there are two questions。

 one is how do you design an M at all， forget the physical constraints you need let's say I just ask you to design an M such that given Mx you can recover x that and then the algorithmic question is okay now now that you know Mx like let's say you know Mx equal to B。

 can you find x which is sparse。How do you find solved system to get a sparse？professor yes。

 so in general will there be a unique solution to Mx equals B or will there only be like a unique solution when we have the K sparse constraint Okay。

 great question actually right so the key sorry so note that x has N coordinates。Right and think of。

T， the number of measurements you have is like K log n。Right， much smaller than N。Okay。

 you're trying to recover an n dimensional vector。By using roughly k measurements。

 this is just think of K measurements， K is like let's say cube root 10 like much smaller than N。

So there won't be a unique solution for Mx equal to B because clearly you only have。

You only have let's say， Klog N equations in n variables。

AK and equations and n variables and which will be much smaller than。

So there won't be a unique solution at all。是。あ。I think of case roots as like root n equations and n variables。

It's highly under constraint， but you know that x is case parse。

And if you only look for solution or case parse， we hope to make it unique right。

 we want to design an M so that the x is uniquely determined for case par vectors。

So we're constructing M so that this works where it's not like we know we're a given M we're just constructing it right so there are two parts I guess we want to construct an M for which this works and we have an algorithm right we need an algorithm to becode and construct M and we'll see that there are lots of different choices for M and there's a fairly unified algorithm that works。

分我怎样。Yeah， and constructing M is a yeah is。There is still yeah，'s that's part of the game too yeah。

 okay， thank you。Okay， so right， so the two questions really are does Mx determine X uniquely？

And how do we find it？Okay。So let'， so let's just。You know ignorere the uniqueness for now and let's think about how do we recover。

 how do we solve the recovery problem？Okay， what is the recovery problem， your input is。嗯。

Let's say M x equal to B。And their goal is find case parex。Case pass solution to the system。And。Okay。

 so。So， you know， and that like well see a very natural heuristic for this。

 so but like you've had to write this as an optimization problem。

the natural optimization problem would be， okay， I have linear constraints。

So I have a linearar constraints I Mexico to B。 and what I want to do is to find a very sparse solution to this。

 So let's say I minimize。0 norm of x。Which is， I mean， not really a norm。Is it。

 I don't know if it's a no， I don't think it's a no。

 I'm not sure I have to check it's a number of non zero coordinates of x。Okay。

 so if we had to find the sparsed solution， this is how we would go about doing it。

 we want to solve this optimization problem。Minimize the number of non zero coordinates subject to Mexico to be。

Okay， and in some sense， note that the real， like in term in recovery， the only real problem is。

To figure out which coordinates are on zero， because once you know which coordinates are on zero。

Which coordinates of x are non0？It just becomes like solving a linear system。

So and that's really the only issue here and of course this is not a nice optimization problem because it's it's neither convex nor is it smooth right。

 not convex or smooth。Okay， and this sort of thing happens quite a bit where you want to。嗯。

Sol something goes sparse solutions。And one thing that like one approach that seems to work。

 a heuristic approach that seems to work。Or a trick that seems to work quite often is to replace the zero norm of x。

By the one norm of x。是。Like this is like a。So like you look at the following optimization problem。

You minimize。The one norm x。Which is some overri absolute value of Xi。Okay， subject to。嗯。

M x equal to B。Okay， so first of all， this is I mean now it's a convex program because of a convex minimization。

 you know nice linear print constraintss， this is a convex program。

 we can solve it by many different techniques。But it， like。It turns out that like using the one norm。

You can actually try to find sparse solutions in many cases。Okay and。Why is this true。

 so here's the intuition why this is true。So I have this picture in three dimensions。

So this is three dimensions。And。What I have here is this is the ocahhedron。And he is Dr。 Hidron。

 which is the this is the。L1 ball。So this is a set of all points， x such that the。

 let's say the L1 norm is less than 1。Okay， in two dimensions， the L1 ball looks like a。A diamond。

And in three dimensions， it looks like an octoharon。Okay， so this is the El1 ball and。

Let's just understand how this11 ball looks a little bit more closely like what are these coordinates。

 this coordinate is actually the coordinate 100。See it's1 norm is one。And this one is。I guess0。

 negative1，0。 This one is negative one。0， zero。This is0，0 negative1。

 so you see that these the corners are really the basis vectors。

Like really the truly the maximally sparse vectors， which have only one coordinate non zero。

 they are the coordinates。Okay， and then if you look at the vectors with two non zero coordinates。

 theyre on these lines that are there here。It's like these lines， these edges of the doctorhron。

They are vectors with two non zero coordinates。And vectors with three or more non zero coordinates are actually indeed。

嗯。on the faces are the interior of the faces。嗯。Okay。

 so that's good and so now that's how the El1 ball looks like the corners are sparse and the lower dimensional facet are sparse。

Low dimensional facets like edges， cords and things like that are sparse vectors。Okay。

 so now what are we doing， well， we have this hyperplane mx equal to B。

It's a hyperplane or it's a subspace。This green thing is an mx be subspace and we are trying to see what is the smallest L1 norm。

With which you can satisfy Mexico to me。So one way to think of it is。Like I mean。

 either you can think of moving the this hyperplan closer to the ball or alternately。

 you can think of。嗯。What is the smallest scaling of this L1 ball such that it touches this hyperplan？

So if you scale thisel ball。Up and up it's going to touch the hyperplane at one point and that's the point at which you know you have this minimize L1 norm subject a Mexico to be okay and as you can see intuitive this object is very pointy。

So for most subspaces you try to pick。You actually hit the。

Like the El board will touch the subspace at one of the corners or one of the edges。

 it's very pointing in that sense。So therefore you end up with this situation where。テック。You know。

 minimizing the L norm。Gives us spa vectors。Typically gives you spa vectors。

This is of course not in general true it really depends on my hyperplane if my hyperplane is sort of hitting flat on one of the faces。

 you know you will not hit the points first， but you can for most hyperplanes or a lot large fraction hyperplanes you'll hit your L1 non minimization gives you spa vectors。

So that's why you know this。You know， this sort of heuristic works。Minimizing that one more it works。

Okay。Okay， so that's the intuitive reason why it works and it sort of is a very broadly used technique now。

 like there are tons and tons of places where whenever you're looking for us， you know。

 you have some idea that something you're trying to optimize for as sparse， you just add L1 norm。嗯。

And yeah。Right， there's a。Yeah， and you know， this is of course。

 it's just a three dimensional picture right。Like it's the sort of explanation， which is。嗯。You know。

 it's just。なで。Yeah， it's just to convince oneself that it's okay， this is why this's going on yeah。

Yeah， so。Professor yes does this same intuition hold for higher dimensions as well Yeah it more at more points oh well I think the actually we'll see the following thing。

 for instance， we'll see that if M is random。Like M is random and the dimension is right。

 like well actually prove that if you pick a random Gaussian matrix， this procedure works。

And but the proof doesn't really。It doesn't directly show this intuition there。

the proof that we're going to see does not going to directly show this intuition。

But even in higher dimension like it is sort of true that you will。

Like all the facets of this El ball are kind of。The element board is pointing that if you hit it from a random direction。

 you'll get a fairly sparse vector。Yeah。嗯。Yeah， but we'll see a proof now that this thing works for random matrices。

没。And the in is more or less right there。Okay， so so let's see how it works for random matrices。Okay。

 so， so。All right， so our M is still going to be what we started with in this lecture。

 we have a random matrix with normal entries right normal 01 entries。Like。T by M matrix。

Gusian Gaussian matrix。And I guess we scaled it by one over square root P。几得岁。Okay。

 and why does this whole scheme work for that？So it can actually abstract out what's happening a little bit instead of directly working with random things by there this property we will call it。

 I mean it's called the restricted isometry。Property。嗯。But， you know， really。

 if I had to like you already have language for this， we've been saying， you know。

 this is just preserving。Lths of sparse vectors。That's what it is It's a preserving length of all all vectors in sub space you want to preserve length of sparse vectors。

 So so what is it well okay a matrix。And。Which is an R to the T by it's a t by N matrix。

 let me say it satisfies。K epsilon RIP。If the following holds， if I pick any case per X。

It should be the case that its length is preserve like norm of Mx。

Should be within one plus or minus epsilon of the norm x。ok。Okay， so。All right。

 so we expect random matrices to satisfy this property like we know why why do we so why do we think so well basically because。

You know the set of sparse vectors is not a subspace they're not a subspace， but they。

Nearly a subspace or kind of a subspace in the following sense。Okay。

 so if I look at the set of all spae vectors。Se of all case perspectives。Okay。

I can write this as union over all sets。S。系。If I fix which coordinates and non0 or where the vector is non0 after n coordinates。

 there are some k coordinates where it is non0， if I tell you which k coordinates where it is non0。

Then。It's just a subspace right if I tell you that the first K coordinates are non zero。

And the rest rest have to be0， the rest n minus k to be0 then you know it's just a subspace which is like art a k its a K dimensional subspace。

 so it's sort of union of N2 k different K dimensional subspaces。That's what it is。

So it's really the set of all sparse vectors， union of。Be subspaces。Kid， this is a subspace。

If I call it v sub， it's a subspace of vectors， basically vectors who were zero on every coordinate outside S okay its and there are you know entries case at subspaces。

And you know if I take the union of all of these subspaces。

 then you know that gives me all case parts vectors。Okay， so， you know。

 we already saw how we can produce a matrix that。Handles any given subspace with high probability。俾。

Any k dimensional subspace it can handle with high priority now it's not one subspace。

 but N k different subspaces， but you know it's just union bound。

 it's a union bound over N k different subspaces。So。

Basically in our claim that in our theorem that we have here。About a random matrix and a subspace。

 D dimensional subspace you just do the following you。You pick。B。逗逼。嗯。Right。

 K plus log of N choose k。Or Epsilon Square。If you pick T to be that high。

Then for any given subspace， the probability that something will go wrong is delta or inches k。

Maybe I'll put another delta also here， so theres simplicity。Plus， log de log 1 over Dlta。

Okay so for any given subspace， the pro that you won't preserve distances there is delta or N k so you know union bound over these ensure k different subspaces。

 so you'll get that for every sparsese vector you preserve the length。So if you pick this。

 then with probability1 minus delta。Every case per vector， the length， you know。

 you it sat space all right。 M is all right。Okay。And now you see the dimension you need， well。

 I mean， ignoring the delta and epsilon and stuff， the dimension you need is like order k plus log of N k。

It sort of makes sense that information theoretically， what I need to tell you is。First。

 I need to tell you which coordinates are non zero。There are anxiousK different possibilities。

 a log of that many bits， and then I need to tell you what are the values in those nonzero coordinates。

 so it looks like you need this many bits of information so it looks like K plus log entries case right and that's what you get。

Okay。Yeah， it's a optimal optic constant factor。Okay， so random matrices sat the RIP property。Okay。

 so that's good okay so now the key thing we want to understand is if matrix sidespaces RIP property preserves the length of spae vectors。

 then we want to prove that this L1 norm minimization algorithm actually works。Okay。

 we want to prove that。Yeah。So。Here's alemma I will prove。其实 suppose。M is。Like some RP。re嘅。

Ignore the。真的。Ignore the parameters。 now， just a random matrix。 just。

 let's just think of as a random matrix。 The parameters will be clear rate。 So it's a， it's set。

It's an RIP matrix then。If you give me any case per sex。Okay， like you run our。

Basis pursuit or it's a the L1 minimization。Program。It will recover。Exactly from。From a bit。

From M max， given M max will record x exactly。Okay that's will Brurunna and that says that you know if you pick a random matrix like this。

 it not only preserves length of sparse vectors， this algorithm actually gives you back a sparse sex whenever you。

Gives you back the right， in fact， the correct text。Not just as sparsex， the correct。professorfess。

 are all the entries of M independent Gaussians？

![](img/bd5d76f3366efa5e940866ef3a095826_2.png)

Yeah， yeah， so yes， all the entries effects are independent Gasians。



![](img/bd5d76f3366efa5e940866ef3a095826_4.png)

Yeah， each standard each standard garsians， essentially I'm using the same matrix that we had for starting from Johnson Lynden Strss。

 Lamma， the same matrix throughout。We started with just dimension reduction with Gaussian entries and then we looked at oblious subspace embeddings with the same random entry random matrices and this is another property of random matrices that we are saying。

It's always standard garnet but。You can replace the Gausian by even random plus minus1。

It can replace by random plus minus one main entries。

 all of the things that we said in what the last two lectures hold。

 in fact for most reasonable distributions all of the things that we said the last two lectures hold。

It's not gosh is not super important。Any other questions？Okay， actually one one thing you know is。

About this。嗯。Something about a comment about explicit constructions so here's an example where explicit construction versus random construction is a huge difference。

 so what we proved so far is that if you pick a random Gaussian matrix it actually has this property that it preserves the length of every sparse vector。

嗯。But， we don't know。Any explicit matrix you know which。

It has the same parameters with the same size。Which also preserve which has with the same properties。

 it preserves a lengthospa。嗯。So we don't know how to construct it explicitly as in what do I mean well in like okay。

 suppose you are trying to implement this。You could decide to pick a random Gaussian matrix and okay and hard code it into your algorithm or whatever。

But you cannot be sure that the random Gaussian matrix that you picked。

Satisfy preserve the length of every case per vector， maybe。

It doesn't maybe you have got on the key and you with property delta your matrix can be a bad matrix and it might not work out so of course you could say is there a way to verify whether a matrix satisfies this RP property we don't have an efficient algorithm to verify whether a matrix satisfies RP property either because like how would you verify it we have to sort of try every possible。

Location for these nonzero coordinates and check whether it's fair RP so not only is it so we don't have to verify it nor do we know how to like give you a formula I mean ideal really you hope because they are so ubiquitous these RP mat are so ubiquitous youd expect that you know there's like a formula you know use Mij is equal to Pla and that gives you that has RP property which in many cases is true but we here we don't have RP mat with that。

that nice school yeah。Okay， so let's see how to prove this fact。 it's not that trick here。

 this just it's quite nice， okay。So。是。Al right， so let's think of it in as a contradiction proof by contradiction。

 Al right， so let's say we we minimized this， let's say we have this linear system M x equal to B。

Okay， for which x is a case par solution， x is case parse。

 but we minimize this L1 norm and we get a different x prime。If I minimize L norm。

 subject to a Mexico to B， I get x prime。Okay， and you know， just for simplicity， let's okay。

 so then let's say， you know， let delta be the difference between x and x prime。It's a non0 vector。嗯。

Okay， so then like of course， what are the observations？Well， delta is in the kernel of M。

 so m delta is Mx minus Mx prime that is b minus b， which is 0。SoM delta is 0。

It's like the difference， right？And。Whats well also。I think。そ对。Yeah。

 so let me call this x prime minus x S mode。啊别你。It's kind of nicer。It doesn't matter here yeah。Okay。

 so。这。So。So and of course the length of x prime right， the L1 length of x prime is the smallest。

 so it's length of x plus delta， right， that's x prime。L1 length is smaller than the length of x。

Okay， so the length of x plus delta is smaller than length of x， and then m delta is 0。Okay。

 and you know， just by scaling， you can always assume。

 let's assume that the by scaling we make the L1 norm of delta equal to one， just we don't have to。

It simplifies some calculations。All right， so this is the situation getting。All right， so let。Okay。

 what do we know about x x is case passse。So， let's say S。Is the set of coordinates I。

 where X is non0。Okay， letx S be that。 and so therefore coordinate of s is k that most k or let's say it's equal to k。

It doesn't matter I at mu。Okay， so that's。All right， so now。Okay， what can we say about Delta right。

 let's look at what Delta looks like。So let me， I guess I can draw x like this， this is a vector x。

It has some set of coordinates which are non zero。And the rest are zero。

I will mark the zero coordinates。this is all zero。The rest are zero。

And Delta is something I don't know what coordinates of delta are non zero， so this is S。But。

One thing I know is that when I add x and delta， I actually reduce the norm of x。

The Al norm x goes down。Okay， so like whatever。Stuff Delta has in S bar。

All the stuff that delta has in S bar， that's only adding to the L1 norm。

 it's only adding to the L norm right so norm delta S bar like the coordinates outside outside S。

This just adds。To Noromics。In。If I look at x plus delta is l1 norm。吓。是。It just adds this stuff。

 what stuff is here adds to the El norm。So we know that。All right。

 x plus deltas l1 norm is smaller than x， so adding delta reduces the L1 norm of x。So therefore。

 like within the coordinates of S。This implies Delta S reduces。The L1 norm。

In the original coordinate L1 normm inside as。By at least。

Like whatever the other side increases by it， right？By at least this much。

So therefore we concluded basically that and all we concluded was that the L1 norm of delta inside s is more than the L1 norm of delta outside S。

Okay， so。Delta can't put all its mass outside us because then adding it will only increase the maximum length of x plus delta。

Sa so that this is what like， so all like alternately， just the。L1 norm of deelta inside S。

Is at least half。The total L1 norm of delta。Okay， and this is， you know， we said it's one。

Half times one。给查。Okay that's sir。不行。All right， so that's。

Okay so I mean basically we are going towards a contradiction we're using these facts we want to go towards a contradiction Okay。

 so what is the sort of contradiction we are going for well you know we have this made this delta vector。

Alright， so this deelta vector， we， we now know that it has a lot of。嗯，你 must。

It has a lot of not mass on the。OnOn the S coordinates。There's a lot of us here。ok， and所。做。嗯。Like。

 you know， Delta S is。It's going to use a weak like rough term， Delta is heavy， right。

 Delta s is heavy。And of course， by definition， Dltas is also sparse。

 meaning it's only on K coordinates， right， so what should happen is。的。You know。

 if since delta S is case parts， like it's on K coordinates， M delta S。

 the length of M delta should also be roughly the length of delta S。

So which means M delta s is also heavy。Okay。So then what will the contradiction be。

 well we know that m delta is 0。Which is m delta is just M Delta S plus M delta S bar。

So if this is heavy， then and if you prove that M Dlta S is light。

The data as bar is light and this is heavy， well just show that or they can't cancel out and give you zero。

And that's the contradiction。That's the kind of contradiction we're going for。ok， so诶。All right。

 so so that's the contradiction。 So let's let me show you the full。Argument now without too much。嗯。

慢 to do。Okay， so let me show you the entire argument。Okay， so。So here's what we'll do。你てタデ。

We have our s here。So those are the non zero coordinates of x like they came from that。Okay。

 then we have the rest of the coordinates。Okay so the rest of the coordinates， we will。

Let's just sort them and。嗯。Break them up into chunks of。细。Like 2 k， this is sorted。

In decreasing order。For nonimp order。嗯。The numbers sorted in non decreasing order and chunks of size。

Yeah。Let's say 2 k。Yeah。嗯。听个茶。😔，Allright， so why we breaking it up into chunks of small size。

 the thing is we don't know what M does on really long vectors。

 but like if you ask me what m does on a full vector we don't know if I break it up in the chunks of small size I can actually reason about what m does on it because I know that on case par vectors it preserves length。

So that that's that's basically the idea。 So let's just give these names。

 So let me call these things。 Let me call this。嗯。These chunks， I'll call it B0， B1， B2， and blah。

 blah blah。Okay， so次。Chunks。我 like to。嗯。Okay， so so。All right， so here's observation one。嗯。是。嗯。

Actually that we did so yeah。Yeah。Yeah， so。Like if I look at the first two things。Okay。

 if I look at its2 norm of m times that。Well， this vector is three case parts。

It it has only 3 k non zero coordinates。Because SSK and B0 has like 2k。

And therefore I can just apply the RIP property as in we know its length is preserved by M。

So its length is at least。Let me just write one minus epsilon times the length of。

It's union in basic。Okay， and of course， this is at least the length of。S。Times 1 minus epsilon。

 Thank if I just look at the。And。What is the length of S？你是肚脑。诶。We said that。Thanks。

We said that deelta S， the one norm is at least one。Okay。

 if the one norm is at least one one norm is at least half。

 sorry we said one norm is at least a half。Not here。So therefore， the two norm is at least。嗯。One of。

对啊。如都嘅。Okay， like why is this when it's。For this is alemma， I guess。哦。V， which is in bigger。

If I have an L dimensional vector， its two norm is at least the one。qui then。对。

Two norm is at least the one mounted by square root2。其实 sir。Okay， so that's， that's it。

Right so that that tells me that the first chunk is going to be heavy。

 I'm just going to prove that the remaining chunks are too like to cancel out the first chunk。Okay。

 so let's calculate the length of the remaining chunks。

So I'm going to claim that the length of the remaining chunks。嗯。Even if I add them all up。

This is at most like 0。4 divided by the square root k。😔，啊。So。So it won't cancel it。

 the point is like this is a claim。Okay， if you assume claim， assume claim。

Then you know what what's happening is if you look at m delta， well。

 it's m times the union of the first chunk plus sum over the remaining chunks。

And we know that the length of this guy is at least。1 over root 2 k。

And the length of all of these guys put together is at most。嗯。4 over road gate。

K times 1 plus epsilon times 1 minus epsilon。And therefore， you see that。This is。

The first term is too long。The other terms are too short。To cancelled。And give you 0。A contradiction。

Okay， so。All right， so the only thing I need to prove is this fact。

The length of the remaining chunks， the length of all the chunk。

 the second third and all the chunks later on is small， the total length。

So the totalwi length like some of the L2 norms， yeah it's L2 norms yeah yeah good question thanks it's some of the L2 norms yeah。

So right， when we use with M， we are using the L2 norms because M preserves L2 norms。

 but now we'll bound the L2 norms。

![](img/bd5d76f3366efa5e940866ef3a095826_6.png)

No yeah， thanks， that's a good question。All right， so now you know it's it's very it's a standard fact。

 it's just， I mean， not not a fact it's even。

![](img/bd5d76f3366efa5e940866ef3a095826_8.png)

Just a。Easy observation。So you have these chunks。Okay。

 now what do we know about let's say I pick look at the I chunk B。Okay， if I look at BI。

 if I look at any coordinate there。Because they are sorted in decreasing order。Okay， any coordinate。

In Bab by。Is smaller than。You know， the。L1 norm of the previous chunk。Divided by。

The length of the chunk 2k。Basically all I'm saying is any coordinate。

In the chunk I is smaller than every coordinate in the chunk Ii -1。 therefore sorry L1 now， sorry。

 therefore。Like any coordinate in the chunk I is smaller than the L1 norm of the chunkangkai minus1 divided by 2k。

It it's just these chunks are。う。Decreasing or the coordinates are decreasing so。

So all the coordinates in chunkkai are smaller than the L1 norm of chunkangkai minus12 by 2k。

 so therefore， if I calculate the two norm of the eighthh chunk，Okay， the two norm。 well。

 to get the two norm， I need to add the coordinates， square them， square them add them， right。

 So I take the。There are 2k coordinates there。And each of them。Is smaller than this bound。

The I minus1。Chunk， it's L1 norm。😔，Divided by 2 k。Poull square。Okay， so it's。So， that gives me。

The l1 norm。Of the I minus-1 chunk。Hold square。Sorry good the half and what I mean。也 to the house。

That's the two norm of the eighththe chunk， add up the squares of the coordinates of the chunk and take the square root。

Thanks's very good。是。I so。So basically， I upper bounded the。Two norm of the eighth chunk。

By the one norm of the I minus1 chunk。Ded by square root2k。All right， so that's her。

That's right it' just because it's the coordinates a decrease you get this。And then， you know。

 you just say some over。I equal to one through， sorry。你对边。Let me do it in different color。

 So now you add this inequality over all the chunks。Starting from one。Okay。

 you get the L of the entire delta。Like the al norm of the entire delta mean。嚟啦。嗯。

Divided by square of2。😔，And you know， we started with the L norm of de being one。

 so I get one over root tooking。So that's the bond we had。1 over root2 k is I think 0。4 over root。即次。

It'sFly intu。Any questions on this。It's fairly intuitiveitive。Yeah。

We use the randomness of M to like quite heavily to say that in each of these chunks， the vectors。

 just the vector of that chunk， its length is preserved。So over here and over here。

 we applied m to just these little sparse vectors when we use。That is where length is preserved。

Professor where did the 0。4 come from Oh 0。4 was just one over square root of  two I should put one over square root two here yeah。

是的。I think one of our square two is around 07。诶。Is it？😮，It's square root two over two。

 so it's like 1。4 over two。好呀。嗯。Is up here。啊。哦。Right， okay， there's another factor of two here。

 sorry yeah。I should be okay yeah okay firstly I mean and borrowing the proof the numbers of the proof from this book from this notes by Mattusec which are linked on the page if I was doing the proof I usually never use numbers like two so you should never use numbers like two in your proof should always use hundreds and thousands and so it's very very clear that nothing will go wrong like this but he's being very stingy with this number so really actually this this is not yeah the point is this is not delta。

On the whole， it is Delta and S bar。It's because all the chunks are outside the set。

 it's deel on bar。And we already saw that delta on S is at least a half。

And Delta S bar is at most half。The L1 nomin S bar is at most half。So。

You would use you would get a one over two root two here actually。

 because this is half one or two root two and that is 04， thanks yeah。Yeah， so it's quite stingy。

 It just works out you know， see this is 0。4 and the other one is。

Just a little bit more so everything works out but。嗯。Yeah。

 I think the key parameter to sort of play with here is that。Actuallyly。

 I didn't emphasize that enough is that。嗯。We are going to apply the。

R IPP property on chunks of size 3k here。Because our chunk is of size 2k and s is of size k。

 so we got 3k so in particular in the theorem statement， we said if you have 3k RIP。

 then you can recover case pass vectors。嗯。To do dispro without any of these things being so stingy。

 you should really just do M000 KRIP。And you're want to just have a case per vector so and then you pick chunks of size 000 k and then these numbers are more starkly clear。

嗯。嗯。嗯。Okay， yeah so。Yeah， that's all I wanted to say today the next class actually will look at other applications of not。

Other kinds of embeddings and their applications。That's what we'll do for the next two or three classes we'll look at different kinds of embeddings of matrix spaces we've been looking at mainly L2 so far L2 winning the two norm。

But there are all kinds of metric spaces and embedding one metric space into another is very useful as an algorithmmic tool and look at more of that。

Thank you， Profeor。Can you go back to the theorem statement briefly？So this yeah。

 so this was all essentially to prove that using just the standard L minimization gets you a sparse vector。

 right yeah。So you say this is useful in like MRI is like what is the context of this algorithm and apply like how do you like construct in like how do you like use an M right like how would that work exactly how the algorithm working like in like a sort of private application I guess right so so right so you can prove that even natural matrices like if you pick random rows of a Fourier Fourier random rows of a Fourier matrix like Haard matrix they also satisfy all these nice properties and then it's really like。

Corresponds to。RightSo when you're let's say I mean I don't exactly know the technical details of physical improve。

 but you can think about if you if you're measuring some signal right you can measure any frequency of your choice right you can measure all the frequencies and then of course you can that's what the usual thing is just measure every frequency but you can also decide to measure like some some small number of。

Gandom frequencies are carefully chosen frequencies。

Right and you just need to build sensors for those things。Right， and then that。

That's like having a small number of measurements and recording the entire signal right Okay。

 so you're saying that like if I have a signal that I want to measure and I measure like。

Some subset of frequencies such that the matrix that results from the subset is right this all right has this RIP factor。

 then I can apply this minimization convex optimization function to get back like the overall x。

 assuming that that x is known to be sparse。Yes exactly and and and the point is that I mean the algorithmic aspect is important。

 but I think even the more important just the information the aspect that you don't you can actually at least recover these signals by measuring a small number of frequencies is a big deal and so one like in MRI machines like。

I don't know the details of my， but they are like they also try to build a one bit camera。

So a one bit camera is where you have just a single sensor。

Like a singles like a literally a sensor which you can measure just one bit and I think you can also try to get different linear combinations by time multiplexing that you can。

Take pictures at different times and things like that。RightAnd like for example。

 if you have a move object which is somewhat moving or something else then you can just use this one single sensor to get different measurements of。

X。就。I think the key point is that the number of measurements is very， very small。

 extremely small compared just。Almost as good as the sparssity。出去。I。And algorithmically， actually。

 the L miniization is I it's good， but it's but you know there are there are some greedy approaches。

 which are also。Work Karen。啊。Look arere there cameras that measure the frequency instead of the actual image itself。

 is that a thing？Well， in a sense。呃。Right， in a sense， every sensor。

 like every made sensory build is not measuring。Purely in the time domain or in the frequency domain。

 what you measure always is。Is something which is a combination of times and frequencies it's because just because the way signals are right so like if you have a sensor it's not like it sampled at a particular time instant and shot switches off there's some width of time over which you get the average of the signal over a width of time。

Right and therefore what you really get is not X you'll never get x x of I you'll actually get x of t convol with some thing and so you always every sensor has a time and a frequency measuring or a region of time and frequency。

Right average right is there are there sensors that like measure a specific frequency over multiple like times is that that I don't know know I think yeah I think that'sificing on the time domain it's sacrificing no。

 I think that's actually the more。Like my red that's that's quite natural right I mean i'm sure like I don't exactly know what senses here。

 but that's actually natural that you have senses like that right for you know like every。Like you。

You know， the idea of。Iedance matching like like you know whenever you have a everything has a resonant frequency right so you will you youll measure like it's very easy to construct things that are resonant frequencies like it'll have you behave like a band pass it'll let one signal through one particular frequency through in fact naturally every sensor has a particular frequency which it likes and other frequencies it doesn't like like even our eyes right so you have three different pos like you know the red yellow low and green or whatever right the sensors it really is like three different frequencies。

It's not although a signal is an arbitrary combination of them。Most like you'll say either。

Dueune to three different frequencies right so yeah it's naturally I think frequencies are more naturally I think it's harder to get a pure time domain thing because if you want to get pure time domain thing you have to be uniform or all frequencies right most systems are not uniform or all frequencies every system like some frequencies and doesn't like some frequencies so yeah。

Thank you， Profess， appreciate it。Professor， I had a question in the homeworkbook assignment。

 is it the right time to ask it or actually let me stop the recording actually？



![](img/bd5d76f3366efa5e940866ef3a095826_10.png)