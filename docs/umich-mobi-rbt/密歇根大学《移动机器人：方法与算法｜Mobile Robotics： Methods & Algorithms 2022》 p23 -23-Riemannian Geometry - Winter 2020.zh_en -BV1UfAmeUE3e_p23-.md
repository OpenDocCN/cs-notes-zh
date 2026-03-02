# 密歇根大学《移动机器人：方法与算法｜Mobile Robotics： Methods & Algorithms 2022》 p23 -23-Riemannian Geometry - Winter 2020.zh_en -BV1UfAmeUE3e_p23-

All right， so let's start day two of terrible math lectures。

 so just so you're aware I'm only teaching on Monday and today so if you survive today you never have to see me again and you can go about the rest of your lives and ignore all of this。

Just two more hours of me so on Monday we talked about matrix groups and about how they're useful。

 I mean particularly for talking about rotations， but they're good for rotations， translations。

 any kind of rigid movement I mean they're useful for much more than justice。And we talked about。

 you know you have these matrix groups， what a group even means， what a matrix thing even means。

 talking about manifolds， talking about you know how we can differentiate these things and we differentiate these things。

 you end up on the the algebra and all this garblely book today， however。

 we're going to talk about how we can actually do geometry on these things。

 So if I give you the group， let's say Se or S03 so the rotations we can view this thing as a set in its own right。

 you know the actual whatever this thing is and we can actually talk about how we can do geometry on this stuff。

So today we're going to do a Muummanian geometry， which is geometry of manifolds。

 which is actually if the underlying space is curvy。

So to start with geometry is just a branch of math concerned with points， lion surfaces。

 solids and other stuff， so this is according to dictionary。com。But of course。

 this is a very vague and not very helpful definition。 and of course。

 if you go back to the last slide， we're not talking about geometry。

 we're talking about Rimaning in geometry。 so there's going to be some specificness here。

So the main thing before we get to into this is there are many， many。

 many different kinds of geometry that ask different questions and answer different answers。

So we I'll talk about three real quick here， but we're really only going to focus on one of them。

So the first one is finsler geometry and finsler geometry is where the only thing that you care about is measuring length。

 so if I give you a curve and the only thing you care about is how long this curve is。

 that's what Finsler tries to tackle。Rmanian geometry， on the other hand。

 deals with both length and angle， so what we're talking about today is if your underlying space is weird or curved or warped or whatever。

 you can define what it means for there to be a length to it and you can also define what it means for there to be an angle。

And then the last one is sctic geometry and sctic geometry now deals with areas is its fundamental thing。

 So if you guys have seen Laangian mechanics before。

That's entirely Romanian geometry Have you guys seen Hamiltonian mechanics before？

That's entirely septic geometry， So you've seen these things before in in a very backward background。

Thing。So we're going to try to introduce Riian geometry as easy as possible。

 so what we're going to do is we're going to first just define what angle and length is according to our own notions before we make things weird。

So suppose we have two curves and let's just say these two curves live in R2。

 these are just the plane， so nothing scary is going on， so we have gamma1 and gamma two。

And suppose they cross here at zero。What is the angle there？

How do we compute the angle of two curves， What do we do？So the dot product is well。

 that's not quite the right answer， right， that's pretty close， right。

 But you do is you draw the tangent lines at each of these things right and you can compute the angle between the tangent lines。

 which is essentially the dot product。 But but the actual formula for the angle right is this thing。

So what you do right is you differentiate both curves。

 you take your dot product and then you normalize it by their lengths and then you take the cosine as's the true thing right so the thing to keep in mind here is the way that you find define an angle between two curves is where you got to differentiate the curves you got to use a dot product somehow and you got to use a norm somehow so we're kind of seeing the underlying things we need to be paying attention to our dot products and norms。

And the next thing we're going to talk about is length， of course。

 so if we have a curve that just goes from zero to1， how long is this curve？

Without one is' what I I mean， when I'm looking for some kind of formula like this， right。

 So the dot product of the derivatives is essentially the angle。What idea。

Makes the length of a curve。Yes， so。That's pretty close。

 So the length of the curve is well you just take the velocity， right。

 So the tangent vector at each point， you figure out how long it is and you integrate these。

 So if you integrate the derivative lengths， that gives you the length of the overall curve。Okay。

 so to understand what it means to be an angle of a curve or to be a length of a curve。

 we need a notion of dot products and a notion of norms， okay。

 so everything boils down to dot products and norms。

So really that's what Rimanian geometry studies so but of course we say dot products and norms。

 but as everyone hopefully should at least be kind of aware of the norm is just given by the dot product right so when we say dot products and norms really everything just boil down to the dot product so if you give me a dot product I can tell you what angles mean and I can tell you how long things are。

So this whole quest of Verian geometry is entirely just going to be understanding what a dot product is。

 but it's going to be scarier than that， but essentially it's going to be just understanding what a dot product is。

Right here。And likewise， since Finsler geometry only deals with lengths it doesn't care about angles。

 if you try to get into Finsler geometry， you only care about norms。

 you no longer care about dot products， but I don't really know anything about this and we don't really care about this。

 but if you want to Google it， there's a whole。Thousand0 books you can read on this topic if it intrigues you。

O。So if we have two vectors in our n so two just column vectors， right。

 we can define the dot product as the usual sense by just taking the transpose and multiplying them together。

 right？But of course， we can be a little bit spicier with this if we can do a little bit more generality than just doing a transpose。

And when we make it a little bit more general， we call it an inner product and a word of warning。

 I will use inner product and dot product interchangeably throughout this lecture so if I say one they really mean the same thing okay。

 it's just a way to multiply two vectors together。So if we just start off with a normal vector space so you can just think of RN and column vectors。

 there's no reason to get too general here， anything that takes into vectors and spits out a number is an inner product and there are three rules you need to follow。

 does anyone know what the three rules are that makes an inner product and inner product or that makes a dot product special？

Well， that's depending on it being an RN in RN， every vector has to have n elements in them。And。

That's 2。Death fall under positive definite for armed purposes here。So it's got to be biline。

 positive definite and。That follows for free， actually， from the the， the norm。Sorry， what。

This one so the first thing is goingby symmetric right if you change the order。

 the dot product nothing changes and the way you can think about this right is the dot product is kind of the angle so the angle between A and B and the angle between B and A are the same angle Okay so when you flip the orders of the dot product。

 nothing changes。It's got to be linear。 So if alpha beta just rule numbers。

 you can break this thing apart this way。 And of course。

 you get bilinear from this because you get linear in the first。

 but then you can flip it and you can get linear in the second。

And then the last one is you've got to have positive definite。

 So this just basically says that the only vector that has length zero is a zero vector。

 nothing else goes to  zero。So。Anything that follows these three rules is going to be called an inner product or you know。

 I might slip up and call it a dot product。 It doesn't have to be the transpose rule。

 So the question that immediately should come to mind is we know that you transpose V follows these three rules。

 but how much does this fail in the other direction If we just require these three rules。

 how much more exciting of dot products can we cook up。And the answer is we can get more exciting。

 but not too terribly much so。So let's consider this matrix。

 so it's just a two by2 matrix we're acting on R2， just two vectors。

 notice that if you define the dot product this way。

 so if we just jam this matrix in between the two， this is still going to give us an inner product。

Okay， so I'm not really going to explain why too much。

 but I challenge you to play around with it and we'll see you a little bit later why this is true。O。

So。Basically， what turns out to be is every inner product has the form where you can just stick some unknown matrix in the middle。

 but of course there's a little bit of a fine print on what kind of matrices work for this because of course if your matrix is just a zero matrix。

 then when you plug this and you're always going to get to zero and that's a pretty stupid dot product to work with。

So we have this， and of course this is going to change the notion of geometry in this following sense。

So here what we have is this is the normal metric， so this is just using the normal dot product。

 this shows us two unit orthogonal vectors to each other， according to the way that you should see。

But if we use the metric on the last page with the weird matrix， the two set of vectors over there。

 now those are orthoormal。Okay， so orthoormal still makes sense。

 It just doesn't mean what you think it means。 So the effect of changing this matrix opposed So sticking this matrix inside this product goes along with basically sharingar and rotating and transforming this。

 So it's still a perfectly valid geometry to work with is just kind of your're drunk and you're looking at it。

 Okay And of course， you can make up any of these such mates and the geometry you end up with is perfectly valid。

 It just。Feels odd， and it looks a little bit weird。

 So we can do a little bit of a demonstration to show a little bit more。So， if we。RightWe have。

 of course， if you choose two orthogonal vectors。You can rotate them around however you feel like it。

 right。So no matter what， right， the blue vector and the red vector are always orthogonal unit vectors to each other。

 and we can rotate them as we feel fit， but if we use this funky metric where we stick this matrix M in。



![](img/4fc48424f3acdba9b1f9e0cfffece2cd_1.png)

We， on the other hand， get this thing。

![](img/4fc48424f3acdba9b1f9e0cfffece2cd_3.png)

Okay so at every single point， the blue vector and the red vector both have lengthhal one and they're both orthogonal to each other。

 but it's with respect to a weird dot product Okay。

 so of course you can make up whatever dot product you want and you can make up any kinds of geometries you want like this and all the rules of geometry is still going to follow overbatim is just a little bit odd。

O。But they're fun to look at at the very least。爱。So the question as to what matrices work， well。

 it works if the matrix is a symmetric and positive definite。😡。

So any symmetric positive definite matrix gives you an inner product and any inner product comes from jamming in a positive definite positive definite symmetric matrix。

 so as you see from back here。

![](img/4fc48424f3acdba9b1f9e0cfffece2cd_5.png)

The reason why this matrix works is because well it's symmetric and it's also positive definite if you compute it。

 So the amount of different kinds of geometries you can stick on R N is equal to the amount of different kinds of positive definite symmetric matrices you can use and they're all going to give you valid geometries。

 but they're all going to be sheed or twisted or warped in some sense or one another。对。嗯。

There's a little bit。 physicists don't really like this a whole lot。

 so we require everything to be positive definite， but there can be times where you just require it to be nondegenerate so your matrix can be negative definite if you want。

 and this comes up in called what's called Larenian geometry which is using a special relativity。

 which we're not going to get anywhere near so don't forget about this。

 but some people do care about things that aren't positive definites。

 you can have dot products to give you negative answers but。We're not going to deal with that at all。

So what we've seen is if we're given an inner product or a dot product。

 we can use that to define what an angle means and what a length of a curve means。 But likewise。

 from the past theorem， a dot product or an inner product is synonymous with the positive definite symmetric matrix we stick inside it。

 So the moral of the story is a positive definite symmetric matrix gives you your geometry。

 So asking questions about geometry is synonymous with just picking a matrix。

So if you've seen any thingses between Monday and today。

 it really should just be that everything has matrices。And you're never going to escape them。

 So we're going to use matrices to define the geometry of matrices。

 and it's going to get a little heavy， but just bear with me is' just giving get lots of matrices。

So the rest of this class is basically going to be examining matrices and seeing what kind of geometries we can pop up with these types of matrices。

So the reason why Rimanianian geometry really comes into play is we can use manifold。

 we can actually examine geometry on manifolds and a geometry and a manifold are things that aren't flat so we can actually talk about how long a curve is on the sphere。

 how long a curve is on a donut， what the angle between two things are and such and such right so if you want to fly from here to London you're not really going in a straight line because the earth is curved or how to actually figure out what that curve is all falls under this realm。

And。Basically， how this thing gets encapsulated is before， if we just use， let's say this。

Matrix everywhere。 It's going to be some sort of shielded reality， but it's still going to be flat。

 The way curvature comes in is now where the mates is allowed to change where we move。

So where things are going to get hard as we move around our point。

 our matrices are going to change and as the matrices change。

 that's going to actually make things exciting for us。

But if you also go back to the very beginning of this lecture nothing so if we had our curve gamma and we were curious about the angles and the lengths of it。

 we never once actually cared about gamma， we always cared about the derivative of gamma if you want the angle between two curves you look at the angle between their tangent lines if you want to figure out how long a curve is you integrate the length of its tangent right so as such we're really only going to be interested in gamma dot and not gamma so going back to Monday if we're only interested in derivatives of curves and not the curves themselves what objects are we going to be interested in。

Close， a little bit more general than the algebras。No， these are all examples。Starts with the T。

Ends with an a space。Tangent space right， so we talk about tangent spaces a little bit on Monday。

 we have to talk about tangent spaces a little bit more today because that's what we're measuring from。

So。For these reasons， right we're going to revisit manifold and we also have to put a lot of emphasis on tangent spaces because understanding the tangent spaces is actually going to tell you the information you need about lengths and about angles。

 the manifold itself really doesn't matter a whole lot。So。

This is probably going to be the scariest flight of today if you can get through this I'm proud of you。

 So on Monday we said a manifold is anything that locally looks flat so the earth is a manifold because where we're standing right now the earth looks like a plane right a circle is a manifold because if you zoom in enough on the circle the circle looks like a line and so on and so forth but that is a painfully。

Vague definition， so this is the formal definition。

 so now everyone knows the formal definition of a manifold。

But let's just break this down before you just pass out on me here。

This first line just says we have our manifold M and we can just chop it up into pieces。

 So basically what's going to mean is each of these pieces we can flatten out and it's going to look flat。

 So this is the earth， is each one of these pieces or where each of us are standing and they all look like a plane。

The second line just says there's a function that maps this chopped up piece into flat space such that this is the smoothing out procedure okay so we're chopping it up。

 we're smoothing out each piece and this condition right here takes a lot of staring it to figure out what's going on。

 but this basically says do if you look at the overlap between the pieces that you chop up and you switch between which overlap piece you're on everything stays smooth。

So there's a picture on the next slide that might make this a little bit clearer。Hopefully。

So basically the simplest manifold we can think of is a circle， well， okay。

 the simplest manifold we can think of is a line because a line is just a line and if it looks like a line。

 it is a line， right？But we can make this a little bit more instructive。

 what's going on the last piece。 So we have our circle。 We chop it up into the four pieces， the red。

 green， yellow and blue。 So each of these are our U alphas。 This is like U1， U2， U3 and U4。

 when we go back。So right， so condition one， the U alphas are just the four different colors of these line segments。

Then of course， each of these line segments we can flatten out into an actual line。

 and so if this green curve right here。Is U1， this map right here mapping it to the science site mean it's called Fe1。

Okay， and then so this is the actual line segment。And then the third condition basically just says。

 well。If we're on this overlap。We can either go to the blue line or to the red line。So likewise。

 if we're right here on this red line， we go to this part of the circle。

And then we can go from this part of the circle to this part of the blue line。

RightSo if we define the function here that takes us from this bit to this bit that function is going to be differentiable is all that it's saying So that's by far the most technical piece。

 but it's useful because we want to take derivatives of things and that last case just allows us that derivatives work nicely so you're never gonna have to really deal with this definition but it's at least a good thing to kind of know what's going on but at the end of the day you can just remember it's something that if you zoom in enough it's flat and again。

 we want to be differentiable so there's no corners as well so we don't want to deal with a square because the derivative on a corner with square is going to get us into a little bit of trouble。

Questions about this so far。Yeah， yeah， so when I say the word smooth。

 smooth means' infinitely differentiable， we're just we're not going to deal with any kind of thiss not continue。

 everything's going to be continuous， everything's going to have derivatives。

 we're not going to try that hard。Because you can do a lot of this if you relax those。

 it just becomes a lot more work and we're lazy。Everything is differentiable。All right。

 so basically anything that you can imagine right is an example of a manifold， so for example。

 if you just use Euclidean space， if you just use RN。

 of course RN looks like RN because it is RN so that's a manifold you don't have to do any kind of work the sphere as we said is a manifold because of course the Earth if you're standing out it looks like a plane and the same thing with the taus so the donut is also a manifold right because if you zoom in enough on the surface of a donut that's going be flat。

And a fun fact right is the Taurus is the configuration space for the double pendulum。

 so the double pendulum you can view that as living on this manifold if you want to think of it that way。

So there's this very， very nice theorem and the theorem basically says that anything you can possibly conceive of is gonna to be a manifold because manifolds shouldn't be too scary。

 everything is one and basically let's say you have a function from r and into R then every level set of that is going to be a manifold so long as derivatives don't grow silly so given any function so long as the gradient is not zero。

 all of the level sets are going to be manifolds So basically if you have a thing and you don't know if it's a manifold well if you can describe it as a level set of some function so long as a function is reasonably nice。

 you're going automatically have a manifold。O。So really anything you can think of that's not incredibly stupid falls under this category So an example of this we can formally prove that a sphere is a manifold because we can write the sphere as a level set of x squared plus y squared plus z squared。

 the gradient of this doesn't vanish， therefore its level set has to be a manifold。

 which is of course just a three sphere。So this is a formal proof that the sphere is a manifold。

 but of course we kind of already had intuition on it beforehand。So again。

 anything you can think of within reason falls under this category and in particular。

 all of the matrix groups we dealt with yesterday fall under this category as well。

A point is a zero dimensional manifold。And。I don't know anyone who takes them seriously。

 you just call them a point， but I guess you can count as it as being a manifold。Yeah。

 you can give a point a topological structure， right？Yes， how I guess to count。All right。

 so questions are all about manifolds or just anything that locally looks flat， yeah。

Maanafold is something that looks flat when you zoom in enough。 with these examples here right。

 the earth is not flat。But if where we're scanning the Earth looks flat to us。

 it's like if you have a function back in Calc1， a function is differentiable。

 if you zoom in enough on it， it looks like a straight line。

 so by a function being differentiable that says that the graph of the function is a manifold。

It can be anything that the only rule is no corners。

Because a corner is you can't take a derivative along a corner， but flat or cur anything is allowed。

 The only rule is you zoom in enough， it looks flat。All right， any other questions？Yeah。

 so basically if your gradient can equal  zero， you can have like weird degeneracy things and you can have weird。

 silly things where like。嗯。Your manifold。I of figure how to like。Right， this disc is a manifold。

 right because it locally looks flat， but you could have something。

Like a disc with a hair on it and this technically isn't a manifold because this is two dimensional and this is one dimensional and they don't agree and you can have weird things like this can happen if the derivatives allowed to vanish on your level set。

And you can also have strange things where you can get cups and things to a court occur。

If the gradient is zero， it's not always a death sentence， but if the gradient is non zero。

 you're always fine。But again， you can just use an eight spectrum just to make sure something stupid doesn't happen I mean。

 in practice， I'm never seen anything stupid happen。Anything else？All right。

 so the next point we need is that of the tangent space， so I tried drawing this yesterday。

 but I think this is a better picture than I could draw so right what's going on is you have your underlying manifold which is some kind of curvy thing right you're given them some sort of a curve gamma on it and then the derivative of the curve this is going to be a tangent vector and all possible tangent vectors from the tangent space。

So what we saw in the beginning of class is to measure， let's say the angle between two curves。

 you differentiate both curves， these are going to give you vectors on the tangent space and then now you want to compute the dot product on the tangent space so really when we're doing this geometry we're really interested in this tangent plane tangent space。

 we're not so much as interested into what's going on down here。O。And again， right。

 every possible derivative you can get from taking all of these possible curves is going to give you the whole tangent space。

Yeah， well， also if you make， if you go， if you have the same curve， but you go along and faster。

 that's going to give you a longer tanent vector。So you want to go rotations and speeds to get everything possible because you can fill out the entire plane with tangent vectors if you just rotate。

 that's just going to trace out a circle。And again， if you're not moving。

 if your trajectory is not moving at all， your tangt vector is just going to be like the zero vector so you can get everything you want。

All right， so if we choose a point x in our manifold to think t subx of M just means a tangent space at M is what we call it and as we discussed yesterday。

 Tx of M is going to always be a vector space so you can always view the tangent space as RN which has a severe。

It's severely better than the manifold right， because the manifold you can only say it looks like RN is not actually RN is something curvy。

 but the tangent space always is RN， the tanganent space always is you claim the tangent space is always nice to work with。

 and the dimension of the tangent space and the dimension of the manifold always agree with each other。

Okay， so know what's going on with so if you know the manifolds three dimensional， you know。

 the tananon space has to be three dimensional and vice versa。

 but you always do get in addition that the tangon space is always a vector space。Questions。はい。

So going a little bit back to Monday， right， if we have a lead group， so when I say lead group。

 just think matrixtri group and when I say matrixtri group， just think SO3 or S3。

And if you choose the identity element， so just the identity matrix， right。

 then the elite algebra is going to be given by the tan space of the identity。So in particular。

 if our group is the special orthogonal group so just rotation matrices。

 then the Lee algebra is given by just dis symmetric matrices and is right so this is always going to be a vector space so if you take two sw matrices and the at them together you're going to get a new s matrix and the dimension of this is going to equal the dimension of the underlying。

Lad group as well。So we didn't talk about this on Monday so but the only real Lee algebra we talked about was the special orthogonal one。

 does anyone know what the Lee algebra for the special Euclidean group is。Okay。

 I'll take that as a no。So right， so how did we figure out？What， what this。

 how did we determine what this thing was on Monday， We did a simple computation。

 simple enough computation to compute this。 And remember， we used the fact。That for SON。

These are matrices。Select that A， a transpose。Equals the identity。

And then what we did is we differentiated this thing， and when we differentiated it。

 this popped out the fact。So let's say if we have。Everything followed from these three lines right so what we did is we had our curve that has to always be a rotation matrix right we differentiated that by use of the product rule and then we used the fact that at zero this and this have to be the identity and then what we end up with is that the derivative at zero has to be a Q matrix okay so we can use this exact same idea for the special Euclidean group。

And remember the special Euclidean group。Orless I guess do n， you can be more general。O。

That's actually a reasonably good question。 I'll get back to that after I do this computation。

 but there's a little bit more subtext today。 So the special Euclidean group。嗯。It matrices that look。

Like this。So when we differentiate this， what type of objects do you think we're going to get？

Well three of these should be quite easy， right， when you take the derivative of0。

 what's the derivative of0？0， what's the derivative of one？ what's the derivative of R？

Something skew， right？Now， what's the derivative of P？Well， in this example right here， right。

 what does R represent in the Special Euclidean group？Well， like physically what's going on。

It's a rotation， right， What is P？Ass a translation， right， So when you differentiate a rotation。

 you get something skew。 If you differentiate a translation， what do you get。You get a so like。

 you know。If I throw a marker， it ends up over there and you differentiate it is going to be a vector pointing in that direction。

 right？So it's still going to be a vector。 if the marker lands all the way over there， it's a vector。

 but when it starts to differentiates， it's still going to be a vector。

 So it's going to end up happening when we differentiate this。

 we're still going to get a vector back。And another way you can think about it。I had the marker。

 though。Is you can also think that you have the curve。You get the gamma of tea。Well， let's say RFFT。

Right， whatever the rotation matrix trajectory is， but then you can just say。Let's say， V。Times T。

Right because the point is this thing this thing always has to be a rotation matrix。

 this thing always just has to be a vector。 So of course。

 this thing is going to be a vector and when you differentiate v times t， what do you end up with。V。

 which again， is another vector， right， So you differentiate this component。 Nothing really happens。

 right，Differentiating， this is going to become sked， but this is pretty boring。 So the the algebra。

For the Euclidean group。Is going to be。Let's say， omega v。Is this going to be given by this？

So if you're thoroughly confused about how to do these computations。

 just memorize these two and I don't think you're going to have to know any the other ones for this class。

 but the moral the story is the orthogonal group gives you skew things。

 the special Euclidean gives you skew and translation， but again。

 this translation to be like a translational velocity， not truly a translation。

So one other question that I kind of want to get to。Is if we have ON and SON。Right。

Does the Lee algebras？Eal。And likewise， if we have。EN， so for the the non special Euclidean group。

 does this equal the Lee algebra for the special Euclidean group， Does the special add anything。

On the the algebra level。ItDefinite adds things to the group levels because remember what we talked about。

 the difference between these two things is this thing has reflections。

 and if this things not allowed to have reflections。But in terms of the actual algebras。

 does it matter if you throw out the SR I？But yeah， so these two are not the same。

But are these two the same， are the algebras the same？So who thinks they are the same？

Who thinks they're not the same？Not raising their hand because they're bored。

So it turns out they are the same， and let's explain why they're the same。

And let's be very lazy and only deal with S2。Slash O2。So in terms of geometry， right。

 what is the matrix group SO2？Yeah， but specifically on the plane， right？

So how can you rotate on a plane？Does clockwises are counterclockwises， right？Right。

 so the point is S2。Just equals a circle。Right the angle on the circle tells you how much you rotate。

 if you go counterclockwise， it's going to be an angle and counterclockwise， if you go on clockwise。

 it' going to be an angle clockwise， right。What is O2？😡，Well， clearly O2 contains SO2。😡。

So it contains a circle。But it's not just a circle， it's two circles。Why is it two circles？

This is the reflection circle， this is the non reflection circle right this circle means you rotate by this angle。

 this circle means you mirror first and then you rotate by this angle okay。

Going off of these pictures， right， let's say that this is the identity element and this is the identity element。

So the Lee algebra for S2。Is this line？And the Lee algebra for O2。There's also this line。

So in terms of finding the tan space of the identity you completely ignore this circle because this circle doesn't have the identity so you don't care about this so this is a completely separate thing that doesn't interfere with you at all。

 so we know that these two things have to be equal so in terms of taking the algebras it doesn't matter if you do SON or just ON or SN or just EN okay。



![](img/4fc48424f3acdba9b1f9e0cfffece2cd_7.png)

Because you're only looking at what's happening at the identity and the identity is the same for both。

So SE2， did my computer actually die？Give me a second answer to your question。



![](img/4fc48424f3acdba9b1f9e0cfffece2cd_9.png)

Okay， so SE2 is a little bit scarier and the answer is you can't really drop it you kind of can。

So I will draw it over here because we have room。So SE2。This is a rotation。And a translation， right？

But again， as we saw over there， the rotation is just going to be given by a circle。

What are the translations given by？Its is the plane， right， and you point on the plane。

 you can translate to that point， so this is going to be a plane。Okay， well。

 the filled in plane is not a box。So how do we combine these two notions together？

So this is where you can't really draw things on the blackboard。

 but what the idea is is you want to do like essentially the Cartesian product between these two sets and what you're going to have is you're going to have the infinite plane and at each point on it there's going to be a circle。

And you look。And however you're supposed to picture this together but you have a plane and every single point on the plane does a circle glued to it。

 so you can't draw it， it's some like weird like smeared out cylinder thing。

But you can also think of it as just a playing in the circle holding hands if you want to think of it that way。

I don't have a better answer。And again， then just E2。

 I suppose SE2 is going to be a plane holding hand of two circles。Yes。Yes。系。

So questions about any of this。All right， so this again， we're doing a little bit more recap。

 so this is all just the algebras， which is what happens when you differentiate the identity。

 but again， if you differentiate not at the identity， what happens well。Remember。

 if you just have the curve， the exponential of AT。Right at 0。

 this thing is going to be the identity。 And when you differentiate it。

 A is' going to pop out and you can get a。 Likewise， though if we。Put a G in front of it right at 0。

 this curve is going to be at G， and the derivative at 0 is just going to be G times a。

So if you are working not at the identity， all that happens is you just premply everything by a gene。

 so if you want to look at the tanin space of the orthogonal group， not at the identity。

 you just take a sw matrix and multiply on the left by something that's the orthogonal matrix you're in。

So it looks a little bit different， but all that's going on is you just take your Lee algebra and you just multiplying on on the left by another matrix。

 and that's all that has to go through。 So if you know what's happening at the identity。

 you automatically know what's going on everywhere。Okay， so a S matrix is in a Lee algebra。

 but a rotation matrix times a s matrix is always going to live in some different kind of tangent space。

So。With this formula， then， what is the tangent space of the special Euclidean group somewhere else？

Well， it turns out actually it's a lot a bit nicer。So if we're in the special Euclidean group now。

Our group element。Is going to be rotation element， a rotation matrix and some sort of a translation vector。

 Or if we want to view this in the homogenous coordinates， right， we can view it。

It really doesn't matter， right？And likewise， if we had something in the algebra。So let's call it。

See。This thing is going to be equal to some skew thing。Some vector and then zeros and zeros。Okay。

 so what happens when you multiply these two matrices together。

 well when you multiply these two matrices together。

 this is going to give you something in the more general tangent space and what you end up with。

Is our。P0，1。Omega v0，0。Equals。So the interesting thing that happens here is the P disappears and what you end up with。

 well this thing is something that's in the new tangent space on just the orthogonal group and this thing again is just going to be a 3 by3 vector。

Forms， so this is going to be inside the tangent space。At the point RPp。And SEE。Let's say three。Okay。

 so a general element in the special Euclidean the algebra looks like this and an arbitrary element in the。

Special orthogonal the algebra looks like this， and again。

 you can do these for all sorts of other groups， but these are really going to be the only two。

That you have to care about。So again， if you're confused about how we did this。

 just write down the answers and move on with your life。All right。

So now we can actually get to what Romanmanian geometry is。

So the actual point of Romanian geometry it's a pair。

 and this is where notation is going to get a little bit silly here。

 normally what you call your metric is you normally call your metric G。

 which it gets confusing because we call our group elements G so there's just not enough letters in the alphabet。

But what Romanian metric is is it gives you a dot product on each tangent space。😡。

So we have our manifold， our manifold is made up of all these different tangent spaces， we can do it。

 each tangent space we endow it with a dot product and with this idea this means any curve we have。

 when we differentiate it is derivativemeters are going to align different tangent spaces。

 but we can still compute their norms on each tangent space and then integrate that across and get the length and same thing with the angles we find the point where they cross。

 we compute on the tangent space where they can cross and then we can compute the angles there。

So all this really is is you can think of this as like a varying dot product。

AndAs we see down here right an inner product is synonymous with this positive definite symmetric matrix and up here it just says that at each point we have a metric。

 so really all Romanian geometry is is that every point on your manifold gives you a matrix and that matrix at that point gives you the dot product so really it's an infinite family of dot products or an infinite family of matrices but the important thing is now the matrices can change。

Okay， and this is where things are going to start getting really weird。So before we move on。

 is everyone at least reasonably okay with the reasoning behind this definition， at least？不应那什么法の。

So that down here。So this just says the inner product is given by a matrix， right。

 and this inner product depends upon the point。So really what this is saying is you choose your manifold。

 each point in the manifold corresponds to a matrix， which gives you this。

So the idea of studying inner products is the same thing as studying matrices。

So you're looking at like matrix valued functions on a manifold is the same thing as looking at geometry on the manifold。

There' are no groups we're not looking at any kind of group structure right here。

 this is completely arbitrary。So let's try to do an example because this is a lot of garble to cook。

 so let's consider the sphere。whichch is the easiest。

 not easy manifold and again let's just choose coordinates theta and phi where theta is the inclination and phi or phi is the asziuth。

 so it's basically latitude and longitude okay this picture I saw off for Wikipedia and it also says R because this is forpher coordinates bar just equals one we're going to ignore that。

So the interesting thing here is now at each point in our manifold the sphere is going to be given by fiN theta is for latitude and longitude and this is what the not the mass matrix sorry this is what the dot product matrix is so if you look at this thing is this thing symmetric and positive definite。

It's definitely symmetric， is a positive definite。Yeah， right。

 because one is well one and science squared is always going to be positive so everything is fine here。

 the interesting thing to note is this matrix now changes depending upon where on the sphere we are。

And there are two points on this sphere where things go drastically terrible and where is that and why is that？

Well， what's zero and what's pi？And then theta is 0 and theta is pi， right。

 this thing is going to be zero。And if this matrix has a zero entry here。

 it's no longer going to be symmetric and positive definite。

 but what points on the sphere correspond to theta being zero？

The North Po and the South Po right so basically what this is saying is on the North pole and the South Po things fall apart and it's kind of unavoidable when you do things with manifolds what's going to happen normally is when you get to the end of these regions you end up dividing by zero and bad things happen that's just a fact so this really just means you can't be at the polls but this thing varies。

So what we see is right this is a picture of the Earth under this phi and theta coordinates。

 and as we see right， when we get closer to the North Po and closer to the South Po。

 things fall apart。In particular at the South Pole， the South Pole。

 which is just a singular point in real life， is smeared out to a whole line and that's clearly something stupid is happening and same thing at the North Po and the closer we get to the South Po and the closer we get to the North Po。

 the more things fall apart。But we have a very quantifiable way to say that， right。

 because everything's encoded in this matrix and this matrix becoming singular completely determines why the meator projection is a terrible projection。

So we can actually quantify this a little bit， so what this picture shows is this shows the query for phi and theta between0 and 2 pi and0 and pi。



![](img/4fc48424f3acdba9b1f9e0cfffece2cd_11.png)

And what this is here， so this is going to be at pi and pi over two。

This gives us a set of orthogonal unit vectors on the sphere。

But as we move right the matrix changes and the concept of orthogonal vectors or normal vectors changes too。

 so each of these points， they're orthogonal unit vectors。

 but as the point moves what it means to be an orthogonal unit vector changes as well and as we move down to the south pole。

 what is happening to the blue line。It's blowing up right it's going to infinity right and the fact that that's going to infinity is exactly explaining why the South Po is getting smeared out to infinity。

 so the same thing that this tangent vector is going to get smeared out to infinity as well so all Vermanian geometry really is getting it is you have these things but now not only is your concept of what an orthogonal uni vector is by change。

 but it depends upon where you are and it changes as it goes around and as these things changes you move around describes the fact that the earth is a sphere。

Right。So。The Earth is a sphere which is an example of something called positively curved。

 there's also something called negatively curved。And does anyone know who made this drawing artwork。

 who's the artist？No。Through this coinin created the math for this， but he wasn't artist。

It's a famous， it's a famous artist。Esher， Esher did this。 This is an Eher picture。

 So this is what's called hyperbolic geometry， which you might have heard of hyperbolic geometry。

 I don't know。 It is also what's called negatively curved。

And as you look at here this is a kind of grainy picture but again just Google point create disk Google Esher you can find all sorts of these things what happens is you have this square right here。

 this square is the same size as I'm getting lost here I think this square and then this square is the same size as this squ what ends up happening is the horizon is infinitely far away from us and everything is getting infinitely squished out into the horizon so again if you Google this you can find gifts of it where people move around on it and it's very trippy and lines flip all over the place。

不。What we have， though， is we do get that this is now the matrix that defines the inner product。

 So what happens on this picture back here， the boundary is given by the unit circle。

So we have to lie inside the unit circle because the unit circle is infinitely far away。

And this is the metric we have， so this is the matrix。So again， we're inside the circle。

And what happens when you reach the circle？What happens to the matrix？

It goes to infinity right and the fact that the matrix falls apart when we get to the circle encodes the fact that the manifold kind of falls apart when we get to the circle in the same way that with the math projection。

 the fact that the matrix fell apart at the poles show that the picture fell apart at the poles。

 so the same thing goes here so using this metric defines you this geometry。And。

This is a new picture that we get。 So here again， we have orthogonal unit vectors on this circle。

 And what happens is we move closer and closer to the boundary。

 these things shrink up quite fiercely。And what ends up happening is you zoom in closer and closer to the boundary。

 these things are going to keep getting smaller and small and you can never actually reach it。

Alright， any question on these two geometries。Use just two arbitrary examples because you can draw pictures quite easily。

But the moral of the story is everything revolves around this matrix if you give me this matrix I can draw you pictures like this and we can talk about geometry and discussing how you come up with these matrices that's a little bit complicated of a task that I'm。

Get all that money， teach you or you're just going to never learn。

For now it was just everything is given the matrix， you can do lots of wonderful things。

But of course， you can kind of do this a little bit brute force when you're on a league group now。

 so returning to a league group。嗯。Re that the tangent space at a non identity element is the same thing as just multiplying the Lee algebra by this element。

So therefore we can define the dot product since the。The dot product at a point， right？

It's going to be given by the same point times the algebra elements。

 we can just completely disclose our eyes to all of the Jews。

And if you define a metric on your lead group such that it really doesn't depend upon where you are。

 everything just cancels out， this is called left invari。

So there's a paper by Monie and I that he might talk about it's like point cloud registration。

 garbage， something about lining up pictures， and the way we do that is we use the left andvari metric on this lead group can be used for image registration。

So you'll probably see that later in this course， but this is a very easy way that you can just build metrics on lead groups because if you just build a metric on the Lee algebra and fix that。

 then you're good for the rest of the group。Which is what this is。

So an example of this is if we use the special orthogonal group。Right。

 then the Lee algebra going to be symmetric matrices。So。

The average element in the Lee algebra looks something like this。

And remember we talked about a little bit on Monday。

 this is the same thing as just calling it a three vector beginning to organize it this way。

So what we're going to do is we to find a dot product on this algebra by just taking the dot product of their corresponding vectors。

And normally 90 to 9% of time when people do metrics on S3。

 they just use as normal like dot product one。And you can do this and this can give you a geometry on a special orthogonal loop and you can go about your day。

With this。 So because a lot of times it doesn't really matter what the metric is。

 you just need one to roll with for what we're going to do next。So before we move on。

 are there any more questions？O。So we've talked about this geometry。

 but we want to actually be able to compute useful things with this。

 I mean so far this is cool for drawing pictures and kind of knowing what's going on。

 but you know we're engineers， we have to solve something to make it look like we're busy。

So a very wonderful thing about Romanmanian geometry is this is actually the machinery that's behind gradient descent or gradient ascent。

Okay， so let's say we have some sort of a function， let's say it's on our manifold。

 so a candidate function would be we have a function on our special orthogonal group。

 so on our rotations and let's say we want to find a rotation that maximizes。

Energy or whatever right so in order to find out how to maximize this function means we want to find an element of our matrix group that maximizes this thing and in general that's very very hard to do so the essence what we're going to do is we're going to switch to using gradient ascent which is going to turn this into an ODE problem。

And gradient ascent just says we follow this ODE， which just means that we go in the direction where it's increasing the fastest because everyone should be reasonably comfortable when I say gradient gradient just means the vector that it's the steepest in。

 right？So for example， we're trying to figure out where the maximum of this function is。

 we start off here， the gradient is the vector that points us in the direction of maximal growth。

 we take a step in that direction， we reevaluate and we iterate this and eventually we'll get to this maximum。

O。So everyone aware of this idea is just walking uphill is all that's going on。

 but it turns out what it even means to be up a hill requires geometry， which is a little bit odd。受。

😡，Your next quiz question is suppose we have a function just on our ends so we're ignoring the fact on manifolds。

 we don't want to complicate it too much if I say DF and I say grad F。

 are they the same are they different or what is the difference？Re vector versus convic。

 do you know the fancier language for that？Okay， so one is a co vector，1 is a vector。 yes。

 one is a column vector and one is a vector。 Which one is which。DF is a row vector。

 grad F is a column vector。Okay， but in a little bit more sophisticated language。

 they're going to be called co vector as a normal vector。

 so DF is called a co vector and grad F is called a vector。

So really what goes on is grad F is just a normal vector， there's nothing weird going on。

 this it's just a vector that is just pointing you in the direction to maximal growth。

But DF is not a vector， it is a co vector。So it is a row vector， but this has a deeper meaning to it。

And what it means。Is it actually a function on vectors？Okay， so a co vector。So okay。

 if we think about the differential here， I mean， the differential， we choose a vector。

 which is our direction and our differential at this direction is just going to be the directional derivative right。

 but what we see is DF is a function to each vectors and then tells you the slope in that direction。

So really what a co vector is the co vector is a function on vectors。Not a vector itself。

So when we actually differentiate a function， the natural thing they get is this co vector。

hi is a function of vectors， and we need to find a way to turn this DF into grad F。

And the recipe for doing this requires Romanmanian geometry Okay I mean。

 if you don't think too hard and you're just on our end then yes the transpose works perfectly。

 but as we saw earlier right， the dot product had a transpose in in but we could spice it up by throwing in this M matrix。

 so the same thing can occur here。So the way we turn a cove into a vector is we use the ramanian metric。

 we use a dot product， we use whatever you want to call it okay so what this says is we choose a arbitrary vector V and so Df of V is going to tell us the derivative in this direction which is going to be a singular number number。

Likewise， you can take the dot product between the vector grad F and the vector V and this is going to tell you the number that's a dot product between the two。

 and we define Grd F to be this magical vector so that this formula holds。Okay。

 so the gradient is the vector that dots with everything that lines up with feeding it into the differential。

And as we saw or as it was said about it being。Row versus column。Right， if the dot product。Of U V。

Equals u transpose V。Right， then we know that Df。A V equals grad F transpose。V。Right。

And then this equation right here， while just solving for everything on both sides。

 it just tells us the D。Equals grad F transpose。 So in normal sense， in the normal dot product right。

 this the DF is just a row vector and the grad F is going to be a column vector。But of course。

 we're working on Rimanian things， so this dot product is a hell of a lot more complicated。

 so this relationship is going to be a little bit more complicated too。

 but the underlying idea is the exact same。O。So questions about this。

 The idea is that the transpos of each other， but the transpo is really unpacking the idea of this metric。

 which is not going to be just as simple as a transpose。All right。

 so this leads to what's called the musical isomorphisms。

And I always love that they're called the musical isomorphisms。

 so let V be a vector spacer just think of this as RN or think of it as being R3 or R2 or whatever is's not important。

You define its dual space and the dual space are all linear functions that spit out a real number。

 So if you think about it， if V are row vectors， V star is going to be column vectors because the column vector。

Naturally you pairs up against a row vector and then you just take their products together and that's going to give you a number。

O。So what the inner product or the Romanian metric or the dot product or whatever you want to call this thing does。

 what this does is it finds a way to associate know or column vectors and row vectors and row vectors and column vectors by using this idea right here。

So。You take V for the first one， v is going to be a normal vector。What you do is you take V。

 you turn it into a co vector。By using this isomorphism。

And then what's going to happen when you pair these together， it has to agree with the dot product。

 and then likewise sharp is are going to be the inverse of flat。

 where sharp is are going to start off with a cove， sharp is going to turn it into a vector。

 so these two you take their dot product and that's going to correspond to the normal pairing。

So this is a really weird way to say it， but this is really just a fancy way to say transpose。

But it's a transpose in this more general context。 So as we see from this relationship right here。

 right。You take the differential and then sharp that and that gives you the gradient。

 so the sharp and flat is how you flip between these two different things and we'll see the actual formulas for these on the next on the next slide。

Again， they're not as scary as they seem， but they're very abstract and odd the first time you see them。

But if you're working on normal dot products and nothing scary。

 these are just transpos is all that's going on。All right， so let's go back to the sphere case。

 So we have our metric， which is given by this matrix。Right。

So our dot product or inner product or Romanian metric。

 are they all the same thing as given by this formula where now this thing is this matrix which is allowed to change around right in order to compute the sharpen the flat。

 what we do is what we just use this formula right here and it just works out to here right because what happens。

Is U is a vector。 But if you want to pair it with V， you got to U transpose times M。

 So this thing now is going to be given by a row vector。

 which gives you the actual thing by the metric。 And likewise， P is going to be a row vector。

 And then when you do this big。Bhaha， you're going to end up with a column vector。

 which is going to become a true vector and if you look at both of these equations and you just let M be the identity matrix。

 which the identity matrix is going to give you the usual metric。

They just boil down there purely just the transpose of each other。So this is again。

 this is just a spier version of the transpose with this extra matrix added in。

 but if you just replace this matrix with the identity is just transpose。

 this is just a weird way to say transpose。The question is about these last two lines。

So right in general。If you have your row vector， which is your differential。

 you got to multiply it by the inverse of this matrix and then hit transpose。

 you can't just directly transpose it。So we can do this with the sphere。

So let's say we have our differential， which is just going to be the row vector of the two partials。

 and we want to turn this into the column vector， where you just follow。

This bottom formula right here。And you get this idea for the gradient now。

So in this sense using this geometry on the sphere。

 it's no longer the transpose it's reasonably close to the transpose right if you ignore what's happening here。

 it is the transpose， but this extra turn that pops out is a feature of the metric。

 which is a feature of the fact that the sphere is not flat。O。Questions。Okay。

 so this is all the required stuff we have to get through， but now you get to go into bonus time。

So we've gone through all of this Romanian geometry and a lot of this seems kind of like Garbledygook and we don't really have good reasons for-。

 I mean， it does tell us how to gradients for gradient flow。

 but we haven't really seen that much more to that。

 but it turns out if you've seen laggrangian mechanics before。

 it's entirely just this this is completely synonymous with Lagrangian。So to do a quick example。

 suppose we had a double pendulum。And assume that there's no gravity because when you're throwing gravity。

 things get hard and we don't like things being hard， things are already hard enough in this class。

If you do the kinetic energy of the double pendulum， it's precisely this。But if you notice。

 you can write it this way。You can write it as a quadratic form。

 you can pull out this matrix in the middle。But of course。

 here we have a matrix in the middle which varies this is a Romanian metric。So the double pendulum。

 the kinetic energy for the double pendulum， is entirely just a Romanian metric。

So now we can ask the question， right， does the Romanian geometry have anything to do with this double pendulum？

And it turns out they are exactly the same thing by this wonderful theorem。If you have a laggrangian。

 which is just given the dot product of a Romanian metric。

 then the Oer laggrange equations give you the straight line equations on this curved surface。

Okay I'm not going to explain a proof of that now but again if you Google it you can find the proof so really all that's going on is if you look at Newton's laws of motion。

 all that they really say is things go straight lines that's all it says so when you do this for the double pendulum again now you're going to be on some weird metrics or things are gonna be curved weird but the motion you have of this double pendulum is entirely just going in a straight line in whatever curved space the pendulum things it lives in。

So this is the entire field of geometric mechanics， which is what I do for a living。

 is you take mechanical systems， you try to pose it as a geometry question。

 and then if you know what the straight lines of your geometry are。

 then you know what the path the robots are going to take because the robot's just moving in a straight line。

 but it's moving in a straight line according to what it thinks is a straight line。

So we can do this for the sphere。 So if we go back to what the M was for the sphere。

 this is what the laggrian for the sphere metric is going to be。 So this is the matrix right， the M。

Equals 10，0，1 over science squared。Right sorry， sine squared。RightSo if you take this as your metric。

 you're going to get that for lagrangion for the sphere。

 you jam this into the or lagge equations and you get these two things and these two ODEs you get are going to describe what a straight line on the sphere is so what is a straight line on the sphere called？

That's more general Bayed is a geodesic。Great circle right so these are so first of all。

 or lagge equations are called geodesic equations because they give straight lines。

 but in particular these two ODEs give you great circles on a sphere。

So what we can do is we can plot them。Right and this is the same picture of the sphere we had earlier。

 this is the solution of these two ODEs on the sphere。 So these are actual straight lines。

So they don't look like straight lines in real life of course， because I mean they don't look flat。

 but the reason why these don't look straight is because the earth isn't flat， the Earth is curved。

 So if you actually put this and glued on a globe， these would be straight lines on the globe。Okay。

 so a very nifty thing that you have is if you know what the metric is。

 you can figure out what the straight lines are just by using the ortho lagge equations。

 if you haven't seen the ortho lag Grandnd equations， don't worry about it。

 but this is one of the reasons why youring geometry is very wonderful is you can very easily solve what these things have to be。

Okay， and that is it， are there any questions and if you want， I can talk a little bit more？

There's one more optional thing I want to talk about， but if you're bored with me， you can leave。

 I don't care。这差不多 way。So the big point is there's the image registration problem。

 and I guess we can talk about that littleic because I think mine is going to talk about that。

 but that's be later in the semester， this is all preliminary stuff。

And this is why I hate teaching engineers that they always ask why？No doesn it？

So let's say for image registration， we'll do this very quickly。

And right what we have is we have two pictures and we want to line up the two pictures。O。

So let's say， and when we say pictures， what we have is we have x and z are point clouds。

Okay and a point cloud is just a collection of pixels so the problem is you give me a two collections of pixels which tell me a three- dimensional image and I want to figure out how they overlap a little bit's right if you have two pictures of a room and you take a picture of a room。

 you take a picture of room over there， you're going have two separate point clouds。

 but if you line them up you can figure out how you move between taking pictures so it's good for odoometry。

Everyone happy with the setup。So what we do。Is we have SE3。And these are the allowable motions。

Because again， if you， if you take a picture of the room and then you move and take another picture of the room。

 the way the camera moved has to be rigid， the camera is not going to disappear in itself or bend。

So the question is which？H and SE3。So what translation and rotation maximally？Overlas。

X and H times z。So you take the image Z， you move it by H and you want to figure out which H gives you the best overlap between these two pictures。

 and if you can figure that out， then you've solved the registration problem okay but again。

 now what we have is we have something on our lead group。

So the way we propose it is we make some sort of a function， let's call it F。

And then we define some kind of like overlap function。Between x and Hz。Okay and again。

 defining what this takes takes you know， a couple hours to do。

 but we can define what this is and mine is going to teach you this later in the class。

 but the point is we don't care what this actual thing is we just care about intuition for why you care about lead groups。

Then what we're going to do is we want to find the maximum。

So the image registration problem now can be put about as a maximization problem where you want to maximize this function over all of these rotation or all these rotations and translations。

Okay， but then going back a whole bunch of slides。Right the way we're going to find this maximum is we're going to find the maximum by using gradient ascent。

 So what we're going to do is we want to find the ODE。H dot equals grad F。

And if we can solve this ODE， then this ODE is going to tell us how to maximally overlap the pictures。

But the problem now is this thing right is going to lie inside。The algebra。

 and you have to be able to make sense of wrangle with all of this。 So the big reason。

 at least in this class why this stuff is gonna to be useful is you're gonna use it to build gradient flows for these image registration problems。

 So if you have anything where you want to find the maximum the best rotation， the best translation。

 the best of both a lot of times you can phrase it like this and the way you actually solve the problem is you use a gradient flow And the way you do this gradient flow right is again you got to fix a metric on the algebra to turn right Df。

Into grad F requires a algebra， you get this equation and of course you have to integrate it yeah。

I have no clue what that means， so now。Yeah， that was mostly him。Well， so the cost function， So F。

Takes in a rotation and a translation and gives us back our measure of how overlap they are。

 So I want to maximize this。But to maximize it， we're going to use this gradient info which is differentiating it and differentiating on this is going to pop us down to the algebra。

 so to maximize this thing it's going to require the algebra as it's going to require Armanian geometry to do this whole procedure。

But this is a very long story， and I think if you look on an archive that you know mine puts like a 30 page paper up or something recently so you can do it it's just it's a long story。

But the tools to answer this。Is， is today and Monday。Well。

 what we're doing is we're maximizing their overlap。

 we define a way to measure the overlap between two pictures， and if we maximize their overlap。

 then we say that you know they're best aligned。Yeah is just's a rotation and a translation。

How do you define Euclidean distance between two point clouds？Pre them all up。Well see this feature。

 it does not require their two clouds to have the same number of points。

 and it does not require us to know the association between them either。All right， anything else？

So I apologize that today and Monday were probably absolutely terrible on your end。

 but this was just a lot of abstract stuff we had to get through。

This big mind never miss class again， and you'll be fine， yeah。

My impression is you have to have a good understanding on the orthogonal group and the Euclidean group。

 particularly in three dimensions because they live in three dimensions， their Le algebras。

 and at least a good intuitive understanding of why grad and D are different and how to flip between them and what this matrix is。

So I mean， intuitively you have an idea kind of everything。

 but in terms of actually being able to put pen to the paper and do things it's just the orthogonal group and especially cl group is really the only thing you have to have a good command on。

对。也。So for this analogy。For the double pendulum there's no potential energies so no gravity there's no controls。

 so you get a geodesic so you get these straight lines that there's no potential no controls。

 if you add in potential and controls， the answer is almost the same it just makes it a little bit longer of a story so you can look up into it is the idea that the intuition similar it's just a longer story。

 but you can definitely add controls to it， it just changes what's happening。



![](img/4fc48424f3acdba9b1f9e0cfffece2cd_13.png)