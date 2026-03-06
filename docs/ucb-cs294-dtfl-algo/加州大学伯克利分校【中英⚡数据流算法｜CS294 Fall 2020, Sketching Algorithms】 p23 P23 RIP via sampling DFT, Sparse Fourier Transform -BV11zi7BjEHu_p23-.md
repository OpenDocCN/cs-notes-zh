# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p23 P23 RIP via sampling DFT, Sparse Fourier Transform -BV11zi7BjEHu_p23-

![](img/fe5fa73c8db50a85540dda0964011e4b_0.png)

Allright。So welcome to the second to last lecture， Wednesday， I believe there are no classes。

 it's a university teaching holiday because of Thanksgiving。So next week。

 Monday will be the final lecture。And then next week， Wednesday。

 we're going to start with project presentations， so those will consume three days of class time next week。

 Wednesday and then the following Monday， Wednesday。Okay， so today， what are we going to talk about？

I want to talk about the sparse Fourier transform。So the idea is。We're giving a signal。不是。

Lets say query access。To a signal。X in Rn。嗯。😊，Oh is my。

I think there's a wfi issue here just give me a second my iPad is。唉啊。嗯。

Not connected to a fast Wiifi network。So what's like。Okay， good。Sorry about that。嗯。Okay。

 so we're giving query access to a signal Xa that's n dimensional。And。We want to compute。

The Fourier transformer X。And for the purpose of this lecture， I'm going to define。

F is the is the discrete Fourier transform defined to be let's say F UV is。Omega1 over end。

Ohmega to the。You times V。Where omega is equal to e to the2 pi I over n and sorry just one second now that I'm connected to the proper Wifi network。

 I have to plug this in。同意。Okay， so。So maybe I'll put a minus here to the minus Uv。

 which implies that the inverse。Is just omega to the U Tu fee。ok。嗯。Now we know that you know。

You want to be fast。We can achieve。and log in time。Va the fast Fourier transform。

 which I'm not going to cover。We covered it in 170 for those of you who have taken it here。Um。

But in applications， oftentimes。The 4ier transform is sparse， so it's approximately sparse。

So the question is， can you go faster？What if。Exat。Is maybe approximately or exactly。Sse。ok。

And I know I mean the discrete forier transform comes up all over the place in signal processing i'm not going to try and elaborate in all of them because。

First of all， I'm not an expert in all of those sub areas but。I guess there are just too many。

 I think there's this there's this list somewhere of kind of top 10。

Top 10 algorithms of the maybe of the 20th century and the FFT is up there because it's so widely used。

One that I is。Know a little bit about is like applications to image compression so you've seen in the lecture notes hopefully。

The picture of me drinking from a baby bottle， and you can see that if you took the 2D hard wavelet transform of that image。

It became approximately sparse， the image almost became completely black。嗯。So。

Natural images are approximately sparse in the 2 d hard wavelet basis and in fact I think my understanding is that's the basis for JpeG 2000。

 so Jpeg there's not just one Jpeg standard there there's been some iteration。

 so I think Jpeg 2000 uses。Harre wavelets to compress I mean the idea is。

As I just so why is it's why can you compress if it's approximately sparse if the image is approximately black。

 well things that are close enough to being black， the RGBs close enough to 000。

 you actually just zero out and then you only store the locations and the magnitudes of the non zeros or of the things that are。

Far enough away from being zero， so that's the source of compression。Why is the FFT？

Or why is the DFT related to compression？Also for image compression， not JPG 2000。

 but the original JPEG， which is from the 90s。W whichch I think is the more popular standard。

 like if you open a JPEG it's probably using it's probably using the original JPEG standard。嗯。

So if you were to take an image and do a 2D DftT to it。

You would actually probably not get something sparse， that's my understanding。

But if you look very locally at the image like let's say you only look at eight by eight blocks。

 the original JG JPEG standard actually does exactly that， it looks at eight by eight blocks。

Then imagine a pixels， imagine that the block you're focused on。Well。

 if it's an eight by eight block of pixels， then for I guess many natural images。

It's all part of the same object， like imagine that you have a picture again of me。

Maybe with slightly longer hair drinking my baby bottle again。

If you were to zoom in on like my hair and look at an eight by8 block there。

 it sort of just looks the same everywhere and it looks sort of like periodic right like I have a hair here then some amount of space to the right of it I have another hair sticking up and then to the you know and they're all the same color so locally it just looks like this periodic pattern。

And kind of that periodicity is why locally you expect to have a dominant frequency。

So that's the basis of JpeG compression is you basically take not they don't take the dftT they take the discrete cosine transform so instead of instead of writing。

Your signal as a linear combination of complex exponentials。

 they write it as a linear combination of cosines， but a cosine of course is just the sum of。😊。

Of two complex exponentials divided by two， I guess， right？So I mean， in fact。

 there's a relationship between the discrete cosine transform。And the discrete Fourier transform。

 I think you can compute the DCT by artificially blowing up your signal by a factor of two or four or something like that and then computing the DFT of that signal that will give you the DCT。

So in any case， bottom line。J image compression like JpeEG that's exactly what it does it breaks up your image into these eight by eight blocks it computes the DCcT of each block and then that's。

😊，For most natural images， that's approximately sparsed and then it truncates all frequencies that have small magnitude。

Okay that have a small amount of mass on that frequency。

 so that's why it's lossy because of that truncation。And similarly with the wavelet transform。

 that's that's how you would make it lossy and save even more in compression。

 you would truncate things that have low。Low RGB values after you do the wavelet transform。

So does that make sense， at least you know， some intuitive sense for why？U。

Why DFTs or DCTs are useful for image compression。Actually。

 just to make sure people are hearing me right， this is my mic is on okay yeah okay good。

So right I mean and it's not just image compression it's also like I think I believe the MPG standard also uses the DCT audio compression。

 there's all audio compression standards that are based on doing DFTs。

So it's a widely used compression thing， compression standard。Compression tool， okay。But yeah。

 if you think of like all these applications。Kind of the main thread throughout all of them。

 like for compression is the reason that the DftT is useful for compression is because for a lot of natural signals。

The Fourier transform is sparse or is approximately sparse， right？So knowing that。

 you could ask the question well。You know if the thing i'm trying to get out only has a you know size k it's approximately K sparse so i'm looking for a K sparse for a transform at the end of the day do I really need to spend n log n time to compute a full FFT is there perhaps an algorithm whose runtime is you know closer to k or some function of k as opposed to being some function of n okay so。

😡，So let's say it's approximately K sparse。If approximately case bars。Can we compute。

Or approximately compute。Ex hat in， you know。Some， you know。

 maybe k or some function of K times polylo N time。I I'd be great。

That'd be faster than the FFT for like applications that you actually care about。

Of course in JPEG it's not clear that that's very useful because N is only really 64 if you're dividing things up into8 by8 blocks。

 then you're locally doing FFT DCTs on 64 dimensional signals。

 so maybe you don't really care about the difference between N log n and K log n depends on what your constants are in your sparse Fouray transform algorithm。

But for larger signals。Where you're doing FFTs， then maybe it could be useful。🤧。Okay， so。

The answer is yes。And kind of there's been a lot of work。

 I'll put the references in the lecture notes， but kind of for a while。

 the best known algorithm was due to Gilbert。We to Krishhnan。And strauss。In 2005。

 and they got something like K times loggged to the fourth of n time。To do as spa story transform。

And。Like what does it mean to approximately compute X hat， I mean。

 I guess you've already seen this kind of stuff with like heavy hitters as well as compressed sensing。

What I really mean here。Approximately compute X hat really means I want some X Tilde。Such that。

X hat minus x tilde， so x tilde is the thing that approximates。嗯。

Exel is the thing that approximates the  Fourier transform， let's say in some norm。

 maybe L2 norm is at most some constant times。Xha tail K。

So very standard kind of compressed senseing guarantee， or you know， you could also ask， you know。

 other norms， like for example， x hat minus x tilde L2 norm。

Is that most oh of like one of a root k times？Xel K。Exhas okay。

This would be like kind of a base L201。Like a whoops like a basis pursuit。Kind of guarantee。

Which we talked about in the last few lectures。Okay。So the first thing to observe is。

Like now we're just talking about like running time， right。

 we're not even talking about memory as we used to talk about in sketching。

If I'm going to take sub linear time in n， remember x is an n dimensional signal。

So if I'm taking some linear time。An N， then。That means that I'm not even looking at， remember。

 I yeah， I'm not even looking at most of the entries of x。

X is the thing that I have access to right I don't actually have access to X hat。嗯。

I'm given as input an array containing the elements of x。So for me to take less than n time。

 that means I'm looking at a very subline number of injuries of X so the first question you might even ask yourself is like forget about trying to optimize computation just in terms of query complexity。

Should it even be possible to approximate the Fourier transform of a sparse or should it be should it be even possible to to approximate？

😡，The Fourier transform of a signal that has a sparse Fourier transform。

By only looking at a subline number of entries in the time domain。Okay， sorry。

 I know that was a mouthful to say。But does that make sense？

Like not it's not immediately obvious that you should be able to even not look at most of the signal and be able to compute its Fourier transform。

So the first thing I want to do is just show you that like a very simple example。

 if X hat actually is one sparse and there's no noise， it's exactly one sparse。

Then you can compute X hat exactly by only looking at two entries of x， okay？

So that's the first thing I'm going to show you， I mean， it's a very simple argument。

And then once you see that， before I talk about， I'm going to talk about getting some linear time in the one sparse case in the case that there is noise。

 so I'm going to show you basically how to get something like this。So even when there's noise。

 you can get some kind of guarantee and I'll show you that when k equals1。

I won't I don't think i'll have time to talk about larger k maybe i'll say something very brief about it。

 but before I before I show you that I want to show you at least that how to get。

Like I'm going to show you that by looking at something like K polylog entries。This is possible。

And I'm going to show it to you by basically showing you that the inverse Fourier transform satisfies the restricted isometry if you sample rows randomly。

From the inverse  Fourier transform， I'm going to show you that that gives you RIP。

 which is something that we used before to basically analyze analyze fast JL， but。

That means that like so you have X hat。Right， what you know is。Approximately sparse。

 it's sparse pulse noise， case sparse pulse noise。Then you take you you take the inverse  Fourier transform of it。

 which is your time domain signal， which you actually have access to and you sample rows of that。

 so you sample kind of time domain entries corresponding to X hat。😡。

And if I can show you that the sampling matrix times the inverse Fourier transform。

With high probability satisfies RIP。Then what that means is given the measurements。

 which is samples from the time domain。You can approximately recover in an L2L1 sense the sparse vector or the approximately sparse vector。

 which for us is X hat。Okay， so it's just a corrollary of what we know about basis pursuit or iterative hard thresholdholding together with the fact that sampling rows of the DFT gives you RIP。

That says that you can actually get this approximate L2L1 recovery guarantee based on sampling a subline number of entries in the time domain now that's great it's just a proof of concept in the sense that it shows thats possible that the information is there。

Okay， the information is there to get the recovery guarantee you want。At least for L2L1。

It's not interesting from the point of view of this lecture because here。😡，You know。

 the main goal is to compute the sparsepo transform in sublinear time。But。

If all you're using is the fact that it's RIP， then how are you going to get how are you going to do the approximate recovery after your measurements。

 you're either going to solve basis pursuit or you're going to use iterative hard thresholdholding or something like that those algorithms are not subline time in the dimension those algorithm you know basis pursuit as a linear program if you actually just use an office shelf LP solver。

😡，Your running time is going to be polynomial and N。

RightEven if you use iterative heart thresholdholding。

 you will get an approximately linear time recovery algorithm。

 but it's going to be approximately linear in N。So if your original goal was to compute the approximately compute the Fourier transform quickly。

Well you're not doing that， you're using you're using time that's nearly linear an end。

 which you could have just used the FFT to begin with anyway。Okay， does that make sense？

Me showing that sampling the Fourier gives you RIP the benefit of that will simply be proof of concept showing that the information is there。

 but algorithmically it's not super interesting for FA quickly computing the sparse Fourier transform。

😡，O。So first off。Show that subline。Time is possible。Whatnt X out。Is exactly。One sparse。Okay。

 so that means let's say a hat u is equal to。It's not zero for some U。And I'm going to do。

 it's going to be convenient to do zero based indexing for the rest of the lecture。So。

I'm going to refer to this as。Brackcade n usually bracket n I use to to mean one to n。

 but for for this lecture bracket n means zero to n minus1 so it's one sparse so exactly one4ier coefficient does non zero and all others are zero。

唔知。😊，So I claim that there's a very simple subline time algorithm now to compute the Fourier transform。

 and remember all you have access to is a， you don't have access to a hat。Oh， I guess I switched my。

 let me， why am I calling it A， I called it X X hat。Okay so first of all。What is x0？ok。

X0 is equal to。嗯。X hat you right， I mean， just remember what。Again。X J。Is equal to。

And little a goes from zero to n minus1。Of Omega， oh me right like this。X hat a times omega。

To the a times J。Right。So if j is equal to0， then omegata to the a times j is 1。

So this implies that x0 is just equal to。嗯。ex at you。Because Xat U is the only non04ier coefficient。

And， meanwhile。呃。Okay， and also it also implies that。And also。

X1 is equal to what X1 is going to be equal to。X hat u times omega to the U。So。We're basically done。

You just have to look at the first two entries of x。

The first one will tell you the value of the Fourier coefficient。

And if you take the second one and divide if you take x1 and divide by x0。

 you get omega to the U so then now you can solve for you。So。嗯。Just like。Can compute。Exact， exactly。

Only looking at。wo entries。Of x。It seems like really any two entries would suffice right yeah that's right that's right。

ok。But yeahです。The scheme is not that robust to noise Okay。

 so if all you know is that X hat is approximately one sparse then this isn't going to work we'll get there we'll talk about kind of another scheme that is more robust。

And it's going to instead of it's not going to be。Constant time。But it's going to be。

 it's going to be like。it's going to be log in log log in time it turns out that you can do log in time as well。

嗯。But yeah， I'll show you log in time to log log in。Okay， great， so before I show you that though。

 I'm going to show you that。😊，So before making robust noise。We'll show that。嗯。Kind of sampling。Times。

I think you need to sampling times。4ourier transform。Inverse  Fourier transform。

And I think you need to also。Divide by root M。Satisfies。二屁。With good probability。

We're here S is going to be this matrix。It's going to be end by end。

It's diagonal and the diagonals are a to 1 up to a to n。

 everything else is zero where a to j is equal to。One with probability。

 I guess M over N and zero otherwise， just meaning like you and they're independent。

So it means that you sample。Inries。Of X。In expectation。Does that make sense？

Kind of so previous analyses in this course like basis pursuit。

Says if one of a rootM SF inverse is RIP。Then can approximately recover。Exha。

Given one of a SF inverse X。But of course。This is just。This part here is just like。Sampling。

Random entries。M x。Right。F inverse X hat is x。So S times that is just sampling random entries。

 so that would that would show that from a subline number of samples。

 there's enough information there to be able to do approximate recovery。Okay。So。Good。😊。

Now let's try to show like。Let's try to prove this， okay， that satisfies RIP。So claim。嗯。And being。

Oh of K times some polylo n。Suffices。To get RIP。with good probability。

And the first paper to show this was by Candice and Tau。I think in '04。

The proof I'm going to show you today is Riddleson inversion。In 0，8。嗯。

And it's been improved since then， but I personally find the Ruddleson version in proof to be the cleanest。

 even though it's been subsumed by stronger bounds。

 stronger in the sense that people have been trying to chip away at the log factors。嗯。

I think the fewest number of log factors now is something like two or three。

And I think rules and inversion in maybe give four， I mean I it's not super important。

 so I don't really remember， but maybe we'll see it as we go through the proof。And it's also。

 I think， a good excuse to cover more with。Supremo of Gaussian processes or Ramara processes because the way that we're going to bound this thing or the way that rubddleson inversion in show that that it gets our IP is by reducing the question to one of bounding the。

Supreum of a Gaussian process or a automacra process so things like Dudley's inequality we're going to see again。

Okay， so proof。嗯。Let kind of。Vs。你知呢。Oh， actually， I'm using us already。This is the sampling matrix。

 we call it VT。Didt be。Projected。Two entries。In T， which is a subset， let's say have1 to n。

So what's the thing that I would like to bound well if I could bound this I'd be happy the expectation over eight does the sampling。

Of the supre over T having size k。Of the operator norm of identity。The identity matrix on T。嗯。Minus。

1 over m times this sum。J goes from one to n of。XJ， okay。

 so let me write what this means XjT XjT transpose so here I'm doing conjugate transpose because I have a complex matrix。

And this is operator norm so here I'm imagining that F I'm going to write F as being。This matrix。

Or it could be F it could be f inverse it doesn't really matter I just want a matrix that's I just want so here i'm talking about f inverse。

 but in general i'm happy to have any matrix M such that M conjugate transpose M is equal to n times the identity so it's a scaling of an orthogonal matrix and at the same time all the entries of M should be bounded by a。

A constant in magnitude。hi is true because all the entries in f inverse are powers of omega。

All of them have complex magnitude， exactly one。Right。

 so an example of an orthogontal matrix that doesn't satisfy this property is the identity matrix because if you scaled it such that such that m transpose m is n times the identity。

 then the scaling would be。You would scale up the identity matrix by a root end factor。

And that if you did that the entries of the identity are not all bounded by a constant in magnitude some of the entries are the diagonal entries are as big as root n and magnitude right so it's not it's not。

You can apply this argument to those so here the only thing we're going to use about this is that it's so called a bounded orthoormal system。

Meaning that first of all， M star M conjugate transpose M is equal to n times the identity。

And then second of all， for all IJ。MIj is like a constant。

So this argument would work on any such matrix， it could be hat Mar。

 it could be  Fourier and verse 48 doesn a matter。And then the xjs are just going to be like the rows。

Of F of your banded orthon system。Okay， does that make sense？So。If you look at this expectation。

 the expectation over the sampling of the soup overall tea of this operator norm。

I just want this to be at most Epsilon。RightIf it's at most epsilon， then by Markov。

 it's at most 10 epsilon。With probability at least 90%。And if it's at most 10 epsilon。

 that means I satisfy 10 epsilon comma K RIP。Okay。So are we all on the same page or does anyone have any questions。

 the name of the game is bounding this expected soup。

I'm sorry that maybe this this should should be an eight a year。Because I'm sampling rows。

 I'm sampling the rows of F inverse。So A to J tells me whether or not Xj was actually kept in the sample。

And M is the number of samples。I don't know if I said that so just to clarify this matrix is the。

Or it actually。诶。So basically if I'm looking what is this in matrix form， it's like a sub matrix of。

I minus F star F or something like that if you just call this if you just call this matrix pi。

I'm basically just I'm looking at the identity minus the T minus pi T transpose pi T， right？Yeah。

Okay， so good。Wait，So， what is the X。X sub J T like what is。Yeah， sorry。

 these teas look a lot like transpos。 This is a poor form。 so maybe maybe to make that look。

I'm just going to all the T's are going to be in parentheses so that means that means I'm taking the vector Xj。

 which is an n dimensional vector。And I'm projecting it onto the subset of coordinates T。

Yeah but what is X？The Rooseveth， yeah， here right here。Oh， X， oh， I see， yeah， sorry。

Is that okay so our real all squared way good so so now we're going to do symmetricization I don't want to spend a whole lot of time on this because it's's it's been in the lecture notes for a couple months now。

 but the idea is with symmetricization I can express this thing itself as the expectation of an independent copy Eta prime of Eta of the same thing1 over m times the sum over J of Eta prime J Xj Xj T T star。

ok。Does that make sense？Like all I'm saying is that。

This thing on the right that I'm subtracting in expectation is the identity on the set of coordinates T。

So I can just replace that identity with an expectation of an independent copy。

And then what I could do is now I can pull the expectation over Eta prime outside。judyensson。

So now this is an expectation over Eta and Eta prime。

And then now I have a difference sum over J ata j minus ata j prime， which is symmetric。

 maybe I'll write this down so this is now at most the expectation over eta and theta prime of the soup over Ts of size k。

And now I can pull out a one over M。Some over J。Ata J whoops。E to j minus ata J prime。X， J， X， J， T。

 T star。And the point is now。The a to j minus a to J prime terms are independent across J and they're symmetric。

 so if I just multiply them each by some random sign sigma。It's equal in distribution。

 so now this is the same as the expectation over eta， eta prime and sigma。

And then now what I can do is I can just do triangle inequality。Okay。

 I can separate the a to J from the A to J prime。And do triangle inequality。

 and now this is at most two over m times the expectation over eta n sigma。Of。

S over J of a to J sigma J a to J。X J T， X J T star。Okay。I'm confused where the Sigma is coming from。

 how are you able to just insert that in there？Because。If I look at the summans and that sum over J。

 the summans are independent of each other， right？And each sumand is a symmetric random variable。😡。

Right， like for example， if I take a Gaussian。Okay， and then I'm and then take， for example。

 take take a random variable G， which is just a Gaussian and then consider another random variable。

 which is G times sigma where sigma is now a random plus minus one。

These two things are equal in distribution， right， because the Gaussian is symmetric。😡，Okay。

 so I'm just saying that the sum ends there are symmetric random variables。

Because Ata J and Ata J prime are independent copies from the same distribution。

So we likely be positive or negative their differences。Like if you look at。

 if you look at like a to j minus ata j prime being alpha。

 that's some event in your probability space。Then what about it being minus alpha， well。

 if a to J and a to J prima just switched places in terms of what they equaled。

 it would have been minus alpha and's equally that should be equally likely because they're the same distribution。

So these are its so every sum is symmetric so if you multiply it by a random sign。

 you' you haven't changed the distribution at all。O。Yeah， so this this insertion。

 it's a very useful technique to know this insertion of sigma is called， I mean。

 this whole technique is called basically symsymmetricization。Which is， you know， you can。

 you can use it to prove a lot of different concentration inequalities because you take some arbitrary thing。

Usually it's like a sum of random variables， the deviation from the mean。

You do this kind of trickery， you artificially insert a random sign into the middle of things。

And then all of a sudden now you can use， you can like， you can condition on the Adas。

And then apply concentration over the randomness of sigma and you know， for example。

 like let's say that this was not matrices， but you know Xjxj star is a matrix。

 but let's say that things were simple and we just had vectors。😡，If you fix the randomness of Eda。

 you condition on Eta， and then you consider the randomness over Sigma。

 you can apply kin' inequality to say that this thing is concentrated， right？

Kinenschens's inequality says the probability that sigma dotted with a fixed vector deviates is bounded。

And the boundedness depends on some kind of variance term。

 which depends on the L2 squared of that vector。Okay。

 the L2 squared here will depend on the As which is random。

 so it'll be you know what you get out of your taildown is itself random。

 but then if you take the expectation over that then you get something nice okay so you can use this kind of argument for example to prove even the turn off bound or Bernstein's inequality basically you artificially insert sigmas。

You take you fit your condition on the on the other things and then you take you take the moment over sigma and you get something nice via kinch and then you continue。

Actually， there' this kind of proof style is already in the lecture notes and the probability review if you look under Bernstein's inequality。

 the proof there uses symmetricization。So okay， let's get back to back to where we were so basically we've reduced now。

We reduced our original thing that we wanted to bound into some kind of symsymmetricized version。

And then now just remember like what is the operator norm right just by and this is a symmetric matrix。

 so by definition the operator norm of a symmetric matrix。😡，Is equal to。

This soup over x of unit norm。Of x transpose Mx。That's just the linear algebra effect。So， oh。

 and sorry， I should say。I erased it， but there's a soup over。诶。

So this is the expectation over Eda and sigma of the soup over T of size K。Okay。

 so let's look at this thing。So we have the two over a times the expectation over Eta and sigma I'm going to write it I'm going to write it as follows I'm going to write it as。

Let's first take the expectation over Eda。And then put the expectation of our sigma inside。

Think of it like that。Of the soup over T of size K of the sum J， let's call it J in omega。

Of Sigma J X J T。XjT star。Where like here mega is just the set of all j such that ata j is one。Okay。

 and now。We just just use the definition of operator norm or the fact that operatororm is the supre over here。

And let's define。Let's define B2 NK。Is like the set of all。

X such that x x is a set of x and RN that have unit norm that are case bars。Such that。First of all。

The algen is 1 and the support size of x is at most k。

So I can write this now as2 over m times the expectation over Eta， which determines mega。

Of the expectation。Over sigma of the soup over all X。In。B2 and K。Of。The sum over J in omega。Sigma J。

Xj dot with x squared。I don't need to write Xt or anything because x is case bars。

Only the entries of xj corresponding to the sparsity of x participate in that dot product。ok。😊。

So lo and behold。Like this is a like if you look at the stuff that's inside of the。

Inside of the brackets。 So basically now inside of these red brackets。

Eda is some fixed thing right you've conditioned on Ada because the expectation over Ada is outside。

In other words， mega is some fixed set。This is a ramac This is a Raammaer process right This is exactly what we've seen before the supreme。

Of a rot market process。so we can use for example duleys inequality，Okay。

 so this thing is bounded by。Up to a constant。2 over M， since I said over there's a constant there。

 I can just say one over M1 over M times the expectation over Eta。

Of the integral from zero to infinity of square log of the covering number of B2 andK。

Of some kind of weird distance function that I'm not going to write down， right？

Of UD right the weird distance function is because like let me let's just call this let's call this distance function row just to be concrete like basically。

Row of X Y is defined to be。The sum over all J and mega。Of。Xj。t X。Squared minus xj dot y squared。

Squared， square root。Because Doley's inequality says if you have a Raudemaer process。

Then what should be there as your distance should be the L2 distance。Right。But。The coefficient。

 it's the L2 it's the what it's the L2 distance between what it's the L2 distance between。

Kind of the coefficient vectors of two different random variables in your process。

 but the coefficient vectors are not just x and y， the coefficient vectors are these funny things。

 right？So corresponding to x， you have coefficient vectors like x1。 x squared， x2。 x squared， x3。

x squared et cetera， corresponding to y， you have x1。 y squared x2。 y squared， et ceter。😊。

So what you want to take is the what you're looking at in Dudley is the covering number of those vectors of those coefficient vectors under L2。

Which is the same thing as covering B2 andK under row。Okay。And maybe it's worth saying， I mean。

 we can write down。Let's expand this out over here some more。

This is inside of that parentheses is the difference of two squares， right？

It's x j dot x squared minus x j do y squared， so it's the difference of two squares。

So we can write it as。Square root of。The sum J and omega。Of。Xj dot x minus y squared。Times。

Xj dot x plus y squared。And then this whole thing is square rooted。Because right。

 this inner thing here is just。诶。Like a squared minus b squared is a minus b times a plus B right so we have x j dot x minus y times x j dot x plus y。

But then we have a squared out here。So they both get squared。And then we have a square root here。

 hence we have this square root here。你该。And then I can write that this thing。Is that most？

The max over all J and omega。Of the absolute value of xj dot x minus y。

That looks like some kind of distance， right？Like if x equals y， this thing is zero。

 if x and y are far apart with respect to dot products with xj。

 then maybe that will be large So i'm going to call this thing。

This thing is going to be the star norm between x and y， so x minus y star。And then what's left。

 what's left is times。Two times the soup over all X over all z， let's say in。Overall， Z in B2 and K。

Of。Of the sum over J and omega。Of xj do z squared。times square root that's the square root。

So that's just by triangle inequality。And then now what I could write is。

So this thing therefore is equal to。诶。X minus y star norm。Times。The soup over over。

Let's call the soup overall T of size K。Of the operator norm of the sum of j in omega。X JT。XjT star。

To the one half。Okay， so I know that was a mouthful。But this thing here。

And I forgot there's a two there， sometimes two。And let's call this soup。

 this soup is some random variable because it depends on omega and omegas random。But let's call this。

Let's call this R。唔。So we we can the row distance between x and I。

 we can bound the row distance between x and y by the star distance times2 R。

So up to this factor of 2 R， we have a bound。Okay， and then now what I can do is I can write。

This is at most。Up to constantant 1 over m times the expectation over eta of the integral from zero to infinity of squared log of the covering number of B2 Nk。

With respect to the staror。And let's just think about this for a second。嗯。

If I so what what I'm saying is that remember I this is a net right So what I'm saying is like if I was you away。

 if I was you away in Roorm。I'm guaranteed to be at most you over2 RA。In Starorm。sorry， u times。

 if I was U away in Rorm， I'm guaranteed to be at most two r times U away in Starorm。

So if I want my star norm covering。To be a roworm covering。

 I had better divide the quality of the net by2 R。 So here I can put kind of U over to R。Do you。嗯。

And then I can do a change of variables。😡，I'm just define。

T to be U over to R and i'll pull a two r out so this is at most kind of R over m well2 r over m but I'm ignoring constants times the expectation over eda integral square log。

OfN B2NK。Starorm。起地机。And then now I'll do one more change of variables。

If I if I divide through the vector by whatever root k。Then the T I need to cover it is T over Roque。

And then now I can do another change of variables again to pull the root k out。

And then this is equal to kind of R root k over M times the expectation over eda of the integral of square root log。

Of the covering number of。1 over route k times B2 and K B2 and K。Starorm。You dou。ok。

So the name of the game now is to basically understand。This quantity。

If we can bound covering numbers of some scaling of the unit ball the unit ball of， well。

 this is actually K barsrse vectors that have L2 norm whatever root k。

We want to cover them under the star norm。With radius U balls。

 and the question is how many balls do we need？If we can if we can get that it the answer okay。

 so I'm just a little sneak preview， the answer is going to。

 of course it has to depend on omega because the star norm depends on omega right the star norm has an omega in its definition right here。

But you know， it's going to depend it's only going to basically depend on like log the size of omega。

So when we take the expectation over Ada。You know， we're just going to。It's only you know。

 that's only going to depend on。Eta is like the thing that basically omega is equal to the number of js。

 such that a to j is equal to1， so the expectation over J expectation over eta of the size of omega is M。

The expectation over Eda of log the size of omega is also something that one can bound so at the end of the day。

We're going to get some bound in terms of K and M， and then we can set M appropriately to make this thing B us in Epsilon。

Okay， so I want to say just a little bit maybe about where to go from here。

 and then I'm going to I'll defer like all details of calculations to putting them in the notes。

But I do think I mean I'm showing this example because I think it's a useful example for you to see again。

 an application of suprema of Raammaer or Gaussian processes and this is an example where。

The problem formulation has nothing to do with Raammas at all or Gaussians at all。

 you just kind of artificially insert Raammas into the picture。😡。

Just so that you can use tools from that literature like use Duley's inequality， for example。Okay。So。

Are there any questions about kind of where we are and like what needs to be done of course I haven't shown you how to do what needs to be done but。

Any questions about that？Okay， so。Less than continue。

So what I said was kind of our original error thing is at most。

R k over M times the expectation over eta times of。Of the integral。

Of skirt log covering number of B2 and whateverque。B2 and K， Starorm。UDU。

 where the staror between x and y。Is defined to be the max over j and omega。Of xj dot with x minus y。

And R is defined to be。The supreum over all T of size k of the sum j in omega of。X J T。X， J T star。

To the one half。嗯。By the way， I think last time was it last time I showed you the square root trick？

Do you all remember that？嗯。That was， oh， I knew it was like the time before last。

 it was when I was wrapping up the proof of KMR。You know。

 bounding the supre of some degree two process involving matrices， right？嗯。If you remember there。

I had some error term， I had the left hand side and I bounded it eventually in terms of its own square root Does that sound familiar。

 and then I solved a quadratic equation and that that gave us a bound on the expected soup。

Does anyoneDoes that sound familiar to anyone， I hope it does。I think so。Okay。

 so just a little sneak preview， I just want to point out that， you know。

You should be reminded of this now because。At the end of the day， we're going to end up bounding。

Right E was what was the original thing that we're trying to bound？

The original thing that we're trying to bound is this。

The expectation over Ada of the soup over tea of this thing。That's what we're trying to bound。

And now what I'm saying is， you know， if you put that， well。Basically。

 I just want to use triangle inequality here to say notice that。This thing is equal to。嗯。

The soup over T and K。Well， let me write it like this。

It's equal to let me multiply by root M and divide by rootM so root M times that soup times the sum over J and omega。

Of1 over M。finally did this。1 over m times the sum over j and omega。Of Xj T， Xj T star1 half。

And then here what I'm going to do is I'm going to inside of this operator norm。

 let me just like add the identity to。And subtract it。

So all I did was all I did was like multiply by root M and divide by root M and add identity and subtract identity so I haven't done anything。

 this is equality。And then now I can use triangle inequality and say that this is at most root M times。

嗯。One plus。The soup。Over T of size K。OfThe operator norm of。

Identity T minus1 over m times the sum j and omega。Of Xj T， XjT star。To the one half。

So this is exactly what kind of what we started off with。

 but now it has a square root in it right because that there's that one half right there in the upper right corner。

 this one half。So when we when we throw in the expectation over Ada in this。

 what we're going to get is this is basically like， oh， this this identity should be a one。

 the operator of the identity is one， right？This is a one。From triangle in quality。

So this is equal to basically Rudom。Times。One plus Ru E。

So at the end of the day it's going to be some， you know。

 we're going to have to bounce some covering numbers we're going to do some Dudley at the end of the day there's an R out here。

And what I just showed you is R itself， when you do expectation over Eda。

 r itself is bounded by root M times one plus root E。So sneak preview。

 we're going to end up bounding E in terms of its own square root。

 and then we can do the square root trick solve a quadratic equation。

Root E has to be smaller than the larger root， so therefore e has to be at most the square of the larger root of the quadratic equation。

Okay， does that make sense for a strategy？Of like where this is going。

Yeah okay so I think I'm you know I want to get back to again actually doing one sparse Fourier transform and sublinear time all of this was just supposed to be a proof of concept showing you that this matrix you know is RP so subline sublinear number of samples into in the time domain is enough information so what i'm going to do is maybe i'll just do one piece of this boundarying the covering number there are like two pieces and then i'll defer the rest to notes。

But basically the idea from here is let's focus on now this thing。

Its like I lost I didn't keep track of my ingrs， you have to keep track of them as you were doing I mean it's from zero to infinity。

 but the point is at some point。Once U is small， once U is large enough。

 like once U is the radius of the set。Then the covering number is one。

 you only need a single ball to cover everything with radiusU。

So log of one is zero right so at some point once C was large enough square log of the covering number is zero。

 which means you can just focus on the integral up to a certain point。

And then what you do is you break up that integral into two parts。

 so you write that this is equal to like the integral from zero to sum you star。

Of that thing plus the integral from U star to like the rest of that thing。

And then you bound these in two different ways， for so for small you。

 what you do is a volumetric argument。Meaning， you just look at， okay。

 so I have I have one of root K B2 Nk。😡，That's just a collection of N choose k different Euclidean balls。

 each of radius one of a roque right that has some volume。

Now I a now I look at a ball of radiusU under the star norm and I try to bound its volume。Okay。

 and then I just look at the ratios of the volumes。

And that gives me a bound on the covering number we talked about this back when we first introduced the notions of packing and covering numbers right。

 so just completely completely by bounding ratios of volumes。And then for larger use。

 you do something called Mori's empirical method。Okay， and is how does that go。

 so let me just focus on this part。Again， I realize I'm not doing all the calculations。

 so I don't expect you to follow all the details of the calculations but。😊。

Maybe you can consider this part of the lecture as just expanding your mind and letting you know of like tool like tools and techniques that are out there and if you want to really see all the fine details i'll put them in the notes。

 but I think what's important again coming out of out of this part is just。

Knowing the kind of architecture of how this proof goes。If I went through all the details。

 I think it would definitely consume like more than one lecture。So for Mori's empirical method。

 here's the idea， so I'm integrating so I'm looking at the covering number。

Of like one over k times B2 and K。Starorm。You do you。This set。

By Kohi Schwartz is contained in the unit ball in N dimensions。Right by Cohi Schwartz。

A K sparse vector has L1 norm at most root k times it's L2 norm here it's L2 norm is one over root k。

 so it's L1 norm is at most one。So all these vectors have L1 norm at most1。therefore。

 this thing is at most the covering number of the L1 ball。Of the under the star arm of UDU。

So Mori's empirical method specifically is a method for。

Boing covering numbers of the convex combination of。Of sets。Okay， under some norm。 So here。

 what is the what is the L1 norm other than。A convex combination of two end vectors， right？

Notice that B1N。Is like the convex combination。Of a set of two nvectors， which is is E1 up to EN。

And minus e1 up to minus E。Right anything in the L1 ball is a convex combination of these two end vectors。

So what is Mori's empirical method， so remember what we want is we want this covering number。

So here's the idea， the idea is。Give an X in this set。Then we call it Z。Given a Z in the set。

Define a distribution， actually， let me not call it Z， sorry。We call W。Define a distribution。D sub w。

Where if， you know， I can write W， because W is a convex combination of these things。

 I can write W as being。Let me call these things like A1 up to AN and A plus1 up to A2N。

I can write W as a sum。J goes from one to2 n of some coefficient。Alpha J times。AJ。

Does that make sense？And what do I know， I know that for all J。

 alpha J is in the interval from  zero to1。And the sum of alpha js is equal to1。

Everything in this set is a convex combination of the ageJs。So what is this distribution Dw Dw？Pick。

AJ with probability， alpha J。And then what I'm going to do is I'm going to pick。Z1 up to Zq。

And z are i。According to the distribution Dw。I'm trying to bound remember。The covering number。

With radius U。Now， suppose。I were able to show you。That the expectation over these Z's。Of1 over M。

 not M。Give me another letter。Whatever Q， actually， I said cur， whatever Q。

sum over J goes from1 to Q of Zj。minus。W。Under Starorm。Is that most of you？

And this is coming from DW。Suppose that。Let me write it like this。Suppose this were true for all W。

Suppose that。There exists a queue such that。For all W in this set。This were true， okay。

I claimed that this would imply a bound。😡，OnOn the covering number。

It imply a bound on this covering number。What would that bound be？Any takers， any guesses？

Are people still there？Yeah， I actually had a question oh yeah。

 the way you've defined B1 to the end up top。If it's a convex combination of these vectors。

 isn't it a polytope rather than a ball， is that what you intended it's a ball under the well okay。

 it's the it's's it is a ball it's the unit ball under the L1 norm。

remember that conve symmetric convex bodies and norms are the same thing。

So like a symmetric polytope， a symmetric convex polytope is a norm。Right。I mean。

 this is just the L1 ball B1N is by definition the L1 ball。

 and I'm saying that the L1 ball is a convex combination of two n vectors。Right， okay， yeah。

 I see I was thinking of the L2， okay。Thanks。The problem so， so okay， here's the like I mean。

 this is， I guess somewhat clever， but。They cover ideas like， okay。

 so what what am I really saying what I'm really saying is that。There exists。A vector of this form。

Which is close to W， it's U close to W under the star norm。How many vectors of this form are there？

There are at most， well， they're exactly equal to actually。There are equal to 2 n to the Q vectors。

Of this form。Right because。Each Zj has to be some AJ， they're only two N Ajs。

So there are only two n possibilities for Z1， two n possibilities for Z2， et cetera。

 so the total number of vectors of this form is exactly2 end to the Q。So if in expectation。

 a random vector of this form is close to W， then there must be， if that's true an expectation。

 it's true on average， there must be a vector of this form that's at least as close as the average closeness。

😡，This is basically like the probabilistic method， there must exist a vector of this form that is U close to W under the star norm。

😡，So my net is simply going to be all vectors of this form。😡。

So I have a net of size to end of the queue。Does that make sense？Yeah。

 it seems like then this is much stronger than just a net。why do you say that Well。

 if the average distance is at most of you？Yeah， that's right。

The average under this distribution D W， which depends on W， right， Oh right， right， right。 So。

 for example， if W equals a one。Then。This this distribution Dw is a singleton distribution。

 so like all the Z's will always equal W right yeah right。

So there's there's actually one average of this form that is close to W， but yes。😊，So now。

 so then the name of the game is just like。How big do you need to make QB as a function of you。

 how big do you you need to make QB for this to hold？Okay。And。I mean， long story short。

 as long as Q is something like。So McCan is basically。Q is at most， something like。I think root log。

The size of omega。Over U squared。Suffices。唔该。So you're going to get a covering number。

That is roughly n to the square root log size omega over U squared。好啊。

And then I mean let me not dwell on this， then you know basically you have one bound on the cover and this also is not again I'll put in the notes showing this claim is actually not that hard I just don't want to I only have 10 minutes left I don't want to spend time on proving it。

If you just expand the definition of what the starn means。And use a union bound。

 that's basically what you get。Okay。嗯。So you have one bound on the covering number， use that here。

Use that bound here， use a volumetric argument。And then you bound you get another bound of the covering number which you use for small U。

 you put it all together， and then you also use this and then you use the fact that R itself can be bounded in terms of the square root of the thing you're trying to bound。

 you get some big quadratic equation， you solve the quadratic equation and then you basically get exactly what I promised you namely that。

It suffices to have K polylogin samples from the time domain。就诶。Well， yeah， basically。

 it suffice us to take approximate like K polyloggan samples from the inverse  Fourier transform to get RP。

Okay， so。At the end of the day， yes， like。K polyloggan samples works。

The problem there is it's not a fast algorithm because you're going to solve basis pursuit or something and it's not going to be K poly log in time。

Okay， so， you know， doing all the math， all the calculations。Leads to the desired bound。But。Then。

 getting。Approximately Xhat from one of a Ru。S F inverse X at， which is just I。This is just x。

Is slow。You know， it's at least。It's at least I me get end time。对。So how do you go fast？He will show。

4K equals1。So what do we want， we want？To recover。Extelda such that。

X tilde minus x hat L2 norm is at most of constant times。X hat times tail。

 let me just square both sides。So this is basically。J not equal to U。Of X hat J squared。We're like。

Ex at you is the largest。Fier coefficient in magnitude。ok。😊，Okay， good。

 so we already saw that if it was if it was exactly one sparse。

 there was like a solution that only looked at two entries of x。So now what do we do？

When it's not exactly sparse。🤧Imagine now。Again， for a second。So another。Method。

When x is exactly one course。And this method is going to be something that's going to be easier to modify to handle noise。

So let's look at。X0 minus xn over 2。Versus。X0 plus x n over two。And let's ask ourselves like。

Which of these is larger？And。I mean， it's going to of course。

 the answer is going to depend on something， but like what information。

 what information do we get if this is larger versus if this is larger amongst these two quantities？

ok。So what do we know， so I'm saying look at x0 minus x n over 2。Versus x0 minus plus x out 2。

So we know that x0 is equal to x u hat。We already said that before。What is XN over2？

Xon number two is equal to x u hat。Times。后名嘅。To the you and over to。So you， I can write as。

2 v plus B。Where B is。EithIt's either zero or one。Basically。

 whether or not U is odd or even B will either be if it's even B will be zero。

 if it's odd B will be1。😡，So I can write this as。X you hat。Times Omega。就 the。诶 two。

2 v plus B and over two。Wch is equal to X U hat？Times。Omega to the VN。Times omega to the Bn over two。

What's it negative get to the VN？It's one right， Omega is a Oomega is an n third of unity， right。

 just remember。Omega is equal to2 E sorry E to the。E to the two pi I over n。

 so it's an n root of unity， so omega to the V n is equal to omega to the n to the V。

 which is1 to the v which is1， so this is one。And what about this thing？

B is either zero or1 if b is0， this is equal to omega to the0， which is one， if b is1。

 this is e to the pi I over n。Which is equal to minus1， so this is either equal to one。

If b is0 or minus1， if b is equal to1。So。Basically。This is bigger。

so let's just think about this for a second， oh， and I just realized this is a little confusing。

This is equal to。X， n over two with entry。This it equal to x。And over two and three。唔。So great。

 so basically this is so this thing here is either is like it's plus or minus XU hat。

And it's going to be plus X you hat。Is going to be plus X you had B is if you is even。

 so this is going to be bigger， this thing is bigger if you is even。😡，This is bigger。The view is odd。

And I mean， not just bigger， but like one of them is going to be one of these two things is going to be zero and one of these things is going to be twice is going to be twice X U hat。

 right？Okay， does this make sense？Okay， so by just looking at these two， we learn one bit of you。Now。

 how do we learn another bit of you？So basically。You know， you is some login bit number。

And we just said we can learn this number，Can learn。By comparing。嗯。X0 with xn over2。

Not comparing those two， but by。By only looking at。Two entries of x。Namely x again。

're going look at x0 and x over two， and you're going to do this comparison in magnitudes these two between the sum and this difference。

Okay， but then how do you learn like the next thing？ok。So。😊，To learn。So learn the next bit。

First of all， without loss of generality。You is even。Okay。And why is that the case？

That's the case because。If you。Like if you why？If you is odd。Then what we're going to do is。

We're going to shift。The signal。Over by one。In other words。

 just define x prime such that like x prime of j is equal to x of j minus1。

So for those of you who are not who don't think about DFTs all the time。

If you if you just do a shift a translation in one domain like in the time domain。

 it corresponds to a phase shift in the。It corresponds to a phase shift in the other domain in the Fourier domain。

 so basically all the Fourier coefficients get multiplied by the same thing， which is mega I think。

It just causes。All fourier coefficients。To get multiplied by omega。Okay。

 so what you could do is like from now on， like when you're trying to learn this next bit。

 what you do is。Every time you access， you know， every time you say yourself。

 like I want to access some entry of x， I actually I actually access the entry that's one off from that。

So I've essentially shifted the vector by one。嗯。Oh sorry sorry that's not what I meant to say I'm trying to make you even so actually what I should have said is the opposite thing what I want to do is the following thing。

I'll define xj prime to be Xj times mega。So again， as I said， if you multiply by mega in one domain。

 you translate by one and you shift by one and the other domain。

 so since I multiplied by omega in the time domain it causes all Fourier coefficients to get shifted by one。

😡，So if after learning the first bit of you， I learned that you was even。Then what I can do is。U。

 from， you know， if I learned that you is even， I'm happy， if I learned that you is odd from now on。

 whenever I want to access an entry of X。I actually whatever I accessed。

 I then post multiply by mega and that corresponds to。A Fourier transform which is shifted by one。

 which means if you used to be odd， now you is even。ok。So without loss of generality， you is even。

And then now what I can do is I can write this implies that kind of。I can write you to be equal to。

You know，4 v plus V where B is you know b is either zero or two。

It's not one or three because know that I know that you is even。Okay。

 and then now what I do is I compare。X0 minus x editor or 4 versus。X0 plus x and over4。

And it's again， the same story， I can basically write exactly the same thing like this。

But with a four instead with a four instead of a two。

 and what I'm going to get is one of them is going to double up and one of them is going to get zeroed out。

Okay， and that， you know， whether it's doubled up or zeroed out is going to tell me whether or not be a zero or two in other words。

 I've just learned the next bit of you。😡，And then again， to learn the next bit。

I without loss of generality， I can assume that all the bits I've learned so far were zero again by multiplying by doing a phase shift in the time domain。

 which will shift things over in the Fourier domain by the appropriate amount to be guaranteed that。

It's a multiple of four now。And then I can learn the next bit by comparing x0 with xn over8。Okay。

 so this is again， is with no noise， but does it make sense？Questions about this？ok。

So why is this a scheme that I can hope to like robustify against noise？

Well the point is I'm not just doing like some explicit computation like before I'm measuring sums and differences and comparing magnitudes。

 so if the noise is like smaller than kind of the difference between these numbers。

 then I'll still get the right comparison even if there is noise okay that's kind of the intuitive idea。

😡，The problem if you try and you know， really do analyze that rigorously is like that's not going to be the case。

喂。You know， it could be the case that the norm of the tail。

Could be larger than the difference between these two numbers you're comparing and it'll throw off your comparison。

😡，Okay。So instead what you do is you to observe， well for that to happen。For that to happen。

 there has to be a lot of noise on either x0 or on xn plus or on xn over4。Right， one of these？

One of these has a lot of basically the noise is contributing a lot to like one of these terms。ok。

But you know that。Whatever noise I mean you can think of the tail of a vector as being the noise right so when I say noise what I really mean is。

😡，Xhat is not justfully concentrated on U， but Xhat has Xha U。

 but it also has plus some mass on other foura coefficients， which I'm calling noise。

 but I'm imagining that that noise has small L2or。😡，And I want to recover Xat up to some error。

 which is big O of1 times that Lton norm。Okay。So what you could say is like whatever noise there is in the Fourier domain also maps to noise in the original domain in the time domain。

 but because the Fourier transform is an orthogonal matrix。

 there's some isometry of the noise the noise is not going to get blown up arbitrarily in the time domain so if you have bounded noise in the Fourier domain you also have bounded noise in the time domain which means that you know that noise has to be spread across these end time domain coordinates okay you can't just have noise everywhere of high magnitude it has to be spread has to somehow be spread across these time domain coordinates。

So the bad situation is that like all the noise in the time domain is concentrated on either x0 or x over four or both。

If that happens， that's really going to mess up this comparison。So how do you fix that。

 you basically fix that by instead。Compare。X R minus x。Mus x。N over4 plus R versus。XR plus。

X ever 4 plus R。For random R。For a uniformly random R。Where。N over4 plus R， I mean it's mod N。

 so you cycle around。And the point is like zero versus n over four is not doesn't really matter all that matters in that argument was that。

😡，You were using two different points that were spaced apart by N over4。

So the point is if you use a random two points that are spaced apart by N over four。

Then kind of in expectation， the amount of noise you encounter on either of those coordinates for a random choice of R cannot be。

 you know， it has it's the expectation is basically kind of what you would expect。

 it's kind of the total noise divided by n。😡，Because the noise has to get spread across these n coordinates and since you're picking a random shift。

The noise got randomly spread。Okay， and you know， if you analyze that carefully。

 you can basically show that this works with good probability and if you want to make it work with high probability。

 you repeat many times with independently chosen R and then you take a majority vote to learn the bit。

Since you need to learn log n bits， you should repeat something like log log n times。

 then by a turn off your failure probability will be one of poly log N。😡，So by a union bound。

 you learn all log n bits with good probability。Okay， so again I know I mean I'm over time。

 which is why I didn't write down calculations， but that's basically the whole idea okay is。

By doing this kind of comparison with a random shift。

You can learn the bits one by one with good probability。

There are log n bits you have to learn each one， you repeat log log n times to get concentration。

 so the total number of entries and X that you even need to look at is only something like log n times log log n。

😡，And your runtime will also be O of login times log login， which is very sublinear， right？

And you still can handle noise。So any questions about like the ideas。

 I know that I didn't write enough of the math for you to have specific line line by line calculation questions。

 but I hope I at least conveyed enough of the ideas that you understand。

What's going on and like kind of what the strategy is。Questions。Okay。

 so if that's if there are no questions， then have a good Thanksgiving break。How do I。



![](img/fe5fa73c8db50a85540dda0964011e4b_2.png)

Thanks， Profeor。

![](img/fe5fa73c8db50a85540dda0964011e4b_4.png)