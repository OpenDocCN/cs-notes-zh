# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p20 P20 Iterative hard thresholding, expanders and RIP1 -BV11zi7BjEHu_p20-

![](img/bc7e99ef8906c34030902c1f6d789240_0.png)

Okay great， so last time we're going to continue on from last time where we're talking about compressed sensing and uniform compressed sensing also known as for all the compressed sensing。

Using RIP matrices。嗯。We talked about how to get RP matrices， one of them is via JL。

 which is what you're showing on the pizza that's due tonight。

 maybe that's why attendance is so sparse today。嗯。And we showed that if you had an RIP matrix。

 if you solved this in your program， also in as basis pursuit。

You'll get a good approximation to the original vector x that was measured。

🤧With this mixed L2 L1 error， so if you recover some x tilde。

 if you look at the L2 distance between x and X tilde。

It's at most one of a root k times the L1 norm of the tail of x， so that's what we saw last time。嗯。

Another thing that， so let me talk a little bit about what we're going to talk about today。嗯。

So at the end of the day you have to solve the linear program right this linear program has。

O of M constraints。Really implic end because if you want to express that L1 norm in terms of linear constraints。

 you need to add two n more constraints， as we said last time。Basically。

 if you wanted to find Yi to be the absolute value of ZI。

 you're going to say that y is at least Z and Y is at least minus Z and then you're going to minimize some of the Y's so you're going to have something like O of M plus N constraints and you're operating in dimension n you need to solvel linear your program that's going to take you some poly MN time。

Okay， which is not incredibly fast， you know imagine that you have an image like the did you all get the image I sent to of myself drinking from a baby bottle？

Anyone out there？Wait， what I sent an image of myself on the piazza。

And I compressed it using the hard wavevelet basis， did you see that？Did know one试。No， no。Oh。

 that's very strange because I made it send immediately to email， but anyways。

Let make sure that it's actually there and now that no one knows what I'm talking about。

Kind of surprised。 So last week Thursday， yes， it's note 33 on Piazza。

 I said 2 D hard wavelet transform。 So I sent an example of。嗯。Images， so images are not。

Images are not necessarily sparse in the standard basis right let's say let's say it's a gray scale image so zero is black and 255 is white Okay。

 so anywhere in between is some shade of gray。So a typical image。

 a typical gray scale image is not all zeros it's not just a solid black image right an interesting image has objects and。

😊，They interesting things to see。Okay， so it's not， it's not really sparse。

 it's not approximately black。But if you do a change of basis， oh， by the way。

 I should say if it's an n by n image that's basically an n square dimensional vector。

 each pixel is a dimension， right？😡，So yes， most natural images are not sparse in the standard basis。

 but if you do a change of basis， they typically most natural images become sparse and that change of basis is like。

 for example， the 2D ha wavelelet transfer。So there's a description of what that is in the lecture notes and I took a picture of myself from my first child's baby shower。

And you know， playing some baby shower game， drinking from a baby bottle。

 it's it's a high def color image， there's not much black in it at all。And then I do。

 I did a 2D hard wavelet transform to it。 and I put that on piazza。 That's note 33 on Piazza。

I thought you all would have gotten an email， but I guess maybe a lot of people missed it or something didn't get sent out properly。

 I don't know， but I just checked it is there。嗯。Anyho？

You can see that after after I run the ha wavelelet transform on it and get the new image it's almost entirely black like you can barely there are some edges you can see in the in the wavelet transform。

 but it almost looks like a totally black image so it is approximately sparse and that's you know that's true of like most natural images basically when you hear the hard wavelelet transform。

There's some non zero mass that corresponds to like boundaries between objects or like colored gradients。

But over large parts of the image where colors are pretty similar for adjacent pixels。

 it just you know the change of basis makes that whole region black。If you want。

re if you're interested in reading more about that。

 you can just look for in the lecture notes when we I talked about the hardware that transform the lecture notes and look at the images on Piazza。

 I also put the code on Piazza I wrote some code in Python which takes any JPEG or PNG file as input and then spits out。

The image after applying the hard wavevelet transforms you can take your own personal favorite photos。

 do a hard wavevelet on it and see what you get out and if it's a natural image。

 if it's not just like totally random colors， then it'll probably come out almost looking completely black。

Okay。Out of curiosity have before I just said it now。

 have any of you ever heard of the Harhelet transform？

Maybe I'll just quickly I'll just quickly draw it here， it's in the notes， but just for your benefit。

So here's an image， right？It's let's say it's a square。

 it's n by N and let's say n is a power of two。嗯。The way I'm not going to describe what the actual basis vectors are because I don't think that's very enlightening。

 I'll just tell you how to convert an image from the standard basis into an image that's expressed in the hard wave basis。

 good。So I'll describe an algorithm to do that change of basis。

If you look at the code that I wrote that's on Piazza。

basically it assumes that each pixel is a number， but of course in reality pixels are colors。

 but colors are actually just twos of three numbers right there's an R value a G value and a B value。

So what you do is you just treat your image as actually a three n square dimensional vector。

So each pixel gives you three numbers RGB， and then you just treat those as three different dimensions and then you do。

You know you do this algorithm on each color separately。

So anyway so what's the change of basis so what you do is you so this is the input image。

And this is the output image， which has the same dimension。It's also N by N。

What you do is you divide up the input image into these two by two blocks。唔该。

So there are basically n over two squared blocks， so n squared over four blocks。

And each block has four numbers in it corresponding to the values of those four pixels。

 so let's call those A， B， C， and D。And what I'm going to do is I'm going to the output image。

 I'm going to divide the output of image up into four big blocks that are each n over two by n over two。

And then they're going to be four these four numbers are going to get transformed into four pixels here。

 So there's one pixel here， one here， one here， one here， just because since it's the top left block。

In the input image， it goes to the top left pixel， each of the output subims。

And what are each of these four numbers？So this one is going to be。A plus B minus C minus D over4。

This one is going to be a minus B plus C minus d over four。

This one is going to be a minus B minus C plus D over four。

And this one is going to be a plus B plus C plus D over four。Okay。

So there's no information lost right so I took in four numbers。

 I did a full rank linear transformation and got out four new numbers。

And you know you can given the four output numbers。

 you can you can solve linear your system and reconstruct the original four numbers too okay so there's no information lost here。

 this is purely a change of basis。And then what I do is I look at this top left part。And I recurse。

Okay。So just some intuition， you know， if those four pixels。

 ABCD are not near the boundary of an object in your image。

Then probably nearby pixels are around the same color。

 that's the intuition for why this works well to compress things， right？

Most natural images have few discrete objects and within objects， the colors are very similar。

So what that means is that。What you kind of expect is that this pixel here。

 this pixel here and this pixel here， basically all of these three regions。

You expect to be very close to zero。Okay， and then when you recurse。

You're going to end up doing the same thing。And then what you expect is like。

 now these three regions。Orre like some， you know， they're still pretty close to zero。

 maybe not as close as before， because now technically， these pixels are not adjacent。 they're like。

 you know， they're too away from each other So you don't expect them to be as similar。

 but they're still pretty similar， so。These three in the top left the bottom these three in the top left corner in the next level recursion。

 these three regions are also probably somewhat close to zero。

And then kind of as you recurse more and more， it kind of gets toward the top left corner。

 gets less and less similar to zero， it gets less black。But you know that area is smaller。

 so overall， most of the output image is going to probably look black。

So this is called the 2D power wavevelet transformer。Of course， when you actually implement this。

You can't actually divide by four because pixels have to have airger you know RGV valuess between0 and 255。

 so you have to you know round it， you divide by four and round but it doesn't really change that much okay。

So it's not it's not so because of that rounding， it is not lossless， it is a bit。

 it is slightly lossy， but you know not too lossy。Does that make sense， by the way。

 just the intuition behind like why this might be a good idea？Are people there testing？Yeah， okay。

 so， yeah， okay。 So hopefully this makes sense。 So anyway。Check out the image on piazza and。

And play with the code yourself and have fun Okay so any any in any case。

How did I get how did I get here basically if you look at that image on piazza that I uploaded to myself。

 it was 2048 by 2048 pixel so it was like。4our million dimensional and grayscale。

 but actually my image was not grayscale it was actually full color。

 so there were RGB values so it was more like 12 million dimensional。

So imagine you're trying to solve basis pursuit on that image you know it's it's a 12 million dimensional LP your algorithm is probably going to be really slow Okay。

 so so the question is like how can you do compress sensing with faster decoding times and I should mention that you know。

Getting the number of measurements low is important because in some applications。

 the number of measurements actually is physical measurements by like a physical device like you're in you're sitting in an MRI machine。

And each measurement is the MRI machine making some measurement， Okay。

 so the longer the more measurements it takes。The longer you have to sit in that machine。

And that that's actually a real problem for children。

 especially because children don't like to sit still and you're supposed to sit still in those machines。

 So if you can get away with fewer measurements， it means the kid has to stay there for less time。

 which is。more practical for doctors to execute and in fact we have faculty here who work on compressed sensing MRI one of them is in the Es department it's professor Mickey lustig I don't know if any of you have taken a course with him。

But we actually have other we have another professor in bioengineering I'm forgetting his name right now。

 but he also does kind of MRI stuff as well， so these are things that are really that really do get used。

In any case， so yes， we want low measurements， but we also want low decoding time because again。

 in this image scenario， you have some 12 million dimensional vector like an image。

 a high re image and you know I can't afford to spend n square time to decode if n is 12 million that's too much。

So people realize this pretty early in the compressed sensing literature and they try to come up with other recovery schemes that were faster than solving basis pursuit。

 faster than solving a linear program。So。😊，We're going to talk about that a little bit today。

So iterative methods。For。Compressed sensing。I'll call it decoding。Meaning。Given。Pi x plus E。Once。

Exelder fast。Such that， x tilde is roughly is roughly x。We didn't talk about this fee last time。

This is fast， sorry my handwriting is terrible。没有一。

Yeah I'll do the analysis including E because it actually is doesn't really change the analysis by much。

 it doesn't make it that much more complicated， but this is post measurement noise。

So as you might imagine， I have some physical device like a telescope like。

Like an MRI machine it's doing measurements on a signal okay but what you read from the machine is not an exact real measurement right the device itself has some noise so it might only measure what you're trying to measure up to some error of you 0。

001 or something right so that difference between what you measure and the true value of pi times X I'm calling that E which is the post measurement noise。

Okay。And you know， there are a lot of iterative algorithms。There's like co SamM。

There is iterative hard thresholding。There's sequential matching pursuit， and of they all。There。

Expandander。Exper matching pursuit I could go on forever honestly。

 there's a whole industry of papers in this area， sub area。So let me not continue。

But just to give you a flavor of it today， I'm just going to focus on one of them。

And this analysis that I'm going to show you is due to Blu and Sa。And Davie's in 2009。

So what is the kind of guarantee that well' firstly write what the algorithm is？

Iterative heart threshold。It takes his input。嗯。Y， which is equal to pi x plus E。And also pi。

 which is the actual pi is going to be some RA matrix that you're using to do the measurements。

And you know it's an iterative algorithm， so it starts off with an initial guess of x。

 which I'll just guess initially as zero。And then it says。For。T equals 0 to capital t。

What I'll do is I'll do some kind of update rule。I'll say。80 plus one。Gets to be。And。Xt。Plus。

 pi transpose。喂。Minus， I think something like pi X T。And then X T plus1。Its to be。They call it。

 so it's called iterative hard thresholdholding because it's an iterative algorithm that keeps doing hard thresholdholding。

 what is hard thresholdholding？It's this operator HK is what's called the hard thresholdholding operator applied to AT+1。

And this is， you know， this is also known as。You know the head vector。So take the vector A plus one。

And zero out all， but the top K coordinate magnitude。And then now you return。Yeah。

 X T plus one or something。And I guess you have to give it as input like T。

 like how long do you want to go for？Okay， so I think that's a very simple algorithm to write down。

Any questions about what the algorithm？Is doing or like what anything you question about the pseudo code？

对。Very good。And you know， in just some intuition， you know， what should you be thinking here？

Intuitively for all these for all these jail matrices， RA matrices， et cetera。

Pi pi is a matrix such that pi transpoposed pi is sort of supposed to be in some way an approximation of the identity matrix right if you think about JL。

Right pi Xl2 norm squared should be roughly。X L tu normum squared。

 but what is Xl tu norm squared that's x transpose x。

What is pi Xl2 bar squared that's x transpose pi transpose pi x。

 so basically I say there's a pi transpose pi in the middle and wouldn't it be great if pi transpose pi was the identity matrix？

Then， we would preserve the norm exactly。Okay， and and you know。

 in the name of the game and a lot of these matrices that we design， whether it be RIP。

 whether it be jail or whatever is come up with some distribution such that pi transpose pi。

 it is the identity and expectation。Um， and， you know， not only is it data and expectation。

 but it preserves whatever you want to preserve for the application at hand with high probability。

So kind of the intuitive picture' always keep in mind is you should always think that pi trans pi is trying to be like the identity matrix。

So if you look at this code， what is it saying？Look at why。ignoregnore that E for now。

 E is this post measurement noise， forget about that。Y is pi X， right， Okay。

 so pi transpose Y is pi transpose pi X。Pi transpose pi x is supposed to be roughly x because pi transpo pi supposed to be the identity。

Meanwhile， pi transpose pi Xt is supposed to be roughly xt。

So what this is what A plus1 is trying to be， A plus1 is trying to be xt plus x minus Xt。

 and lo and behold， the xts cancel and what you're left with x， which is great。

 you're trying to converge to x。ok。And you know we end up doing this hard thresholdholding operator before going to the next iteration。

 and the reason we do it is you know we need to we need to at some point use the fact that pi has a certain property。

 the property we're going to use is the restricted isometry property。And if you keep applying。

 if you keep applying pi to non sparse vectors， then it's hard to say anything in the analysis because RP matrices。

Only work well on sparse inputs。Right， so if you notice here we're applying pi to xt in the for loop。

 right y minus pi xt well xt is k sparse， so we can hope to reason about pi times xt because its it's pi applied to a sparse vector。

嗯。And no that's that's kind of you're going to see it now when we actually do the analysis formally。

 but that's why we keep doing this hard thresholding operator is to keep making sure that。

We're always applying pi to something that's sparse so that in the analysis。

 we can actually reason about it。O。😊，So good， so does the code make sense and does the intuition make sense before we actually。

Do a formal analysis。Okay， so good。Let's get on to a formal analysis then could I ask a question so so are we in the context where like even trying to just solve like Laso is too expensive。

嗯。So Lasso is like L1， it's L1 minimum penalized least squares。Right， but。嗯。

This alone depression lossso was very commonly used for these。Like a sparse problems。

 But when people， when people solve Lasso。I mean， one one okay so one way to look at all these iterative algorithms is that they are solving basis pursuit。

 they're just not solving it via off the shelf in your programming algorithm。

 they're solving it using some iterative algorithm that。

That specifically guarantees that you know that work that。

That works for a specifically basis pursuit， but not general LPs okay I see。Yeah。

 I don't know if that answers your question because even Lasso， I mean， if you just write it as it。

 you know， people don't， I think people don't solve Lasso just by using it off the shelf like conves。

Programming algorithm like a lipoid or something right they they use iterative algorithms as well so I mean I think it's a similar story。

诶诶 thanks yes。Okay， so let me write theorem down and then we're going to improve it so theorem。

And this is due to a sub bloomoming South and Davieies and 09。嗯。查一下。So theorize， suppose。

Pi satisfies。Epsilon comma 3K RP。同远。Um for epsilon less than one over four times。

 of some constant that's going to come up in the analysis similarly with when we're analyzing bases pursuit。

Then for all capital T going to one。We have a bound。X。C plus1 minus x。Elti more is bounded。

 so this less than twiddle means up to a constant factor。

Your error is going to be1 over2 to the t times the l1 number of x。And you know。

 it if this this this term right here is coming from the fact that basically it's because it's because our initial guess for x was the zero vector we chose x zero to be zero if somehow magically you。

We're able to get a better starting point， this could also be improved。

 but you know it's exponentially into a cake anyway。Plus， X K。How to norm， okay， plus。1 over root k。

Exha k。L1 norm plus norm B。So in terms of what here is new。

Compared to what we saw in the analysis of basis pursuit。You know， we didn't have basically。

 of course， the the straight， you know solving the LP didn't have this this term that comes from the iteration。

 we also didn't talk about this when we talked about base pursuit just because we didn't talk about post measurement noise。

But。That has to be there， right？If there's a post measurement noise。

Of norm alpha like you're not I mean that noise could have been anything so you know you're going to have some you're going to have some kind of dependence on on alpha in your in your aerodon when you do the cover。

So and also， I guess we didn't have this term either， right when we talked about basis pursuit。

But I want to first， I want to just show you that that term actually is morally bounded by the L1 term。

 and the reason is just due to shelling Okay， so let me just show you that So lemma。

Let's look at XT 2K。Tll to， I claim that that's at most something like one root Ka。Time X， O。

That mean k here is anything it's just this is just the general fact about vectors and you know in particular that means that you know。

 what that means， for example， is that this part here is at most。One over cover two times。Exhale。

 K two。So， you know， up to changing k by a factor of two， it's dominated by the other term anyway。

If you wanted to have error， that was K and not K2 just。Use an RP matrix that's actually 6 K RIP。

 Okay， and then you would， you know then you would get。Then pretend that your K was actually2K。

So what's the reason for this proof？Let's just， you know without loss of generality。

 I'll just pretend that the entries of x are sorted in descending order。

 so x1 is at least x2 is at least x3， et cea。And then now I'm going to just like I did in previous proofs。

Divide up the entries of X into blocks。So this is， I'll call this like S1。Has size k。And then。

S2 has size， K， et cetera。Okay。And then now when I look at x actually so I said2 k。

 and let's actually make it 2 k。对。Then if I look at。If I look at the L2 arm squared。Exhale。

2 k L2 norm squared is equal to the sum J goes from 2 onward to， I guess， roughly and over 2 k。Of X。

sJ L two norm squared。Okay。Now I can say that this is at most。

The P sum J goes from two onward of so the L2or。Is that most root dimension times the L1 known by crochey Schwartz？

But you know excessJ is actually a sparse vector it only is2K sparse。

 so instead of paying root dimension， you only have to pay root 2 k so this is at most root 2 k。

Times the L1 norm。Xsj L1 norm， and then it's squared。嗯。And then now what I can do is。I can compare。

I can compare each element。So okay， so what is this like let's look at， you know。What am I doing。

 I'm summing up the absolute value squared of like this this thing plus this thing plus this thing plus this thing。

Each one of these things。Is that most the average in the previous book？That's shelling， right？So。

This is at most Ro 2 k， and now is this is Koshi Schwartz。This is showing。嗯。

The sum J equals to onward of。How many entries are in XsJ， there are 2 k of them， so 2 k times。

Each entry there is， well let me it right like this，2 k times。X， S J， Linfinian norm squared。

And what can I say about the afinity norm， the infinity norm is at most the average of the。

It's that most the L1 number of the previous block divided by K， in other words。

 is that most the average of the previous block？So okay。

 so this is not quite showinging yet now let me do showinging。So now let me say shelling。

 so this is shelling。Route 2 k times the sum now J goes from one onward of。2 k times。

XSJ L1 norm over K， and then the whole thing was squared。Okay。😊，Good。So now。Where are we at？

This is a k and the denominator is a K squared。And then there's a root out here So we have K rootane the numerator and a K squared to the denominator。

 So this is equal to one over。Two2 over K， I guess。Times the sum Jake was one onward of。X。

S J L1 norm squared。And then now let's just square root the whole thing， so square root this。

 square root this。Squa this。where it is。嗯。S with this。

I feel like though this should have been a square root K， right？But yeah。

 and now the point is just like root A plus B is that mostly like root A plus root B？So this this。

Square root of the sum， I can just apply the square root term wise， and then I'll get the sum over J。

Of XSJ Elor， which is just。嗯。Okay， I see。 I see now what I。嗯。廿期 so。

Very minor thing that I should say actually what I'm going to do is I'm going to make。

In my definition of the SJs， I'm actually going to get rid of。I'm not going to make get 2 K。

 I'm make it K。Okay， and then now， since I have Xle 2 k， I'm starting from J's three onward。Okay。

 and then now this is not a two decay， this is just decay K。So now I feel happier。

And now this is not a two。 This is。 Sorry for the confusion。

So I don't have all those twos everywhere。嗯。So so now I have。The L1 norm overque。

And this J goes from too onward。So I actually have X。Sorry for the confusion about the twos。

 but does this make sense？Do you have any questions？So anyway so good。

 so now let's just try to prove the theorem。对。Okay， so as I defined it， I said。嗯。8 plus one。

Is just defined to be。Xt。Plus， pi transpose， y minus。派 x c。

Or I remember right if I said that y is equal to pi x plus some post measurement noise。

That's the definition of why and let me also define Rt plus one。Or Rt plus1， we define that to be。

And。X minus x d plus1。So this is the residual。So our goal。

 our goal is to bound right if you look at the theorem statement。

Our goal is to build the norm of the residual down what's on the left hand side there。嗯。

So let me make some definitions。So。Some notation actually， so first of all， let me define。So。

 so okay， another thing I want to say too， which is maybe also worth saying in the beginning。

Without loss of generality， I can assume that S is exactly。Case first。Okay。

 why is that Because now that we have post measurement noise， I can write X。The reason is as follows。

 I can write x as being x had K。Plus， xL K。Okay， and then I'll just pretend like this is really X。

And then this is something else， but notice now。Pi x plus E is equal to。Pi X head K。pl。Pi X K。

Plus plus E。And I'll just treat this entire thing。As。Hot measurement noise。Right， and you know。

 what's the guarantee that the algorithm is giving us。

 the guarantee that the algorithm is supposedly giving us is that。Our final。Error and recovery。

Has the norm of E in it， and it also has the norm of XT k in it， the L tumor X K。So， you know。

 this is my new， this is my new life。I'll call it Eilda。ETilda is my new post measurement noise。

 so if we're getting error that depends on the norm of Eilde。

 well the norm of E Tilde by triangle inequality is at most the norm of E。

 which we're happy to have anyway， we don't mind having the norm of E in our recovery error。Plus。

 the norm。Of pi X k。I。What can I say about the number of pi X tailk？How can I control that？

Then at's zero， right？Very small。We don't know that， right？W do you say zero？喂啊。

So Xta k is's like x minus its head。So it's like take the best case force approximation of x。

And then subtract it off， that's X k and pi is this RIP matrix that has 3K RIP。First， let me ask you。

Is X k， is it sparse， is it a 3K sparse vector？It's not right I mean it could be anything we don't know we don't know how far it is。

 but。The key thing to realize is。Kind of the thing that's more important about RIP is that not only do you preserve norms。

 not only do you like not blow up the normal lot， but you also don't shrink the normal lot like the norm of pi X if x is sparse the number of pi X is that most one pulls up sometimes the norm of x。

But it's also at least one minus uppsilon times than number more x， okay？So XT K is not sparse。

 so we can't say that pi doesn't shrink its norm too much， but we actually don't in this context。

 we actually don't care whether pi shrinks its norm if pi if pi makes its norm become zero great that's less error for us because we're trying to bound the normal Eilde right now。

😡，All we want to argue is that pi doesn't increase the norm of X k by much。But in fact。

 that's just true for any RP matrix by the triangle inequality。Okay， so take any RIP matrix。

 give it any vector， which is not necessarily sparse at all。

And I claim that pie can't increase its norm by much。 Why not。

 Because this thing is the same thing as pi times the sum J goes from。let's say。呃，2。

Onward to Nover K。Of XSJ。Else， you。Right so S1 is the largest k in trees in magnitude S2 is the next largest k X3 is the next largest k et cetera。

 so XT k I can write like this， and then this is at most the sum over J at least two of the norm of pi Xsj。

你讲。And today now I can use RIP because these are actually sparse major sparse vectors。

 this is at most you know。By the definition of RP， I'll say square root of one plus epsilon square root just because the way I defined RP it preserves a square norm by one plus epsilon。

 So this is not the square norm it the square root of the square norm So one plus epsilon times is sum over J bigger than two。

Of the norm of excessJ。And then now how can I finish this off？I can do koshi Schwars。

Kshi Schwartz says that there at most one plus epsilon of the sum J bigger than two of XsJ squared square root。

 that's kshi Schwartz。And this， by definition is just the tail vector， the norm of the tail vector。

So this is equal to root one plus epsilon times the norm of XT k。Does that make sense？

So I guess one life lesson to keep in mind is。嗯。This fact that if you just don't want to blow up norms。

 you don't care about you you don't mind shrinking norms， you just don't want to blow up norms。

 then RIP gives you that even for nonse vectors just because you can do triangle inality like this。

So yeah， so good， so basically what I'm saying is if I just pretend that x is actually X head。

And throw pi X k into the post measurement error， just pretend like it's post measurement error。Then。

If I if my new post measurementement noises E Tilde。

 the norm of E Tilde is bounded by the norm of E plus roughly the norm of the tail。

 which is within my tolerance for the kind of error I'm willing to have in the theorem statement。

 right I have both of those terms on the right hand side anyway。So from now on。

 for the rest of the proof， I'm just going to assume that x is actually its head。

 meaning that x is actually a case power vector。嗯。Sorry， I have a question when you apply khi source。

 why don't you pick up a factor of like square rooted D over k？Oh， it's a， let's see， so。Oh wait。

 thats a good。嗯。Actually， you bring up a very good point， I should pick up something， right。Oh。

 you know what？Okay。😊，Yeah that that's not what I should have done here's here's what I'll do and here this will actually fix it。

I can make can make my life even。I am going to do coach s Schwartz。

 but I'm going to do groceryy Schwartz to pick up an L1 dorm。So this is u most。

So this is a case Spse vector， so I can say it set most。嗯。Root one plus epsilon times。The right。

 L2 is at most。嗯。something's a little off here I wanted to say this up so L2 is at most L1。H。Yeah。

 I think what I need to do is I need to shell， sorry I thought I。嗯。Oh okay， okay， wait， let's see。

 here's what I can do。So I， okay， so。Crop yeah， you're right you're right that that's not actually what I should do。

 but I think what I can do is if instead sorry I don't know how I missed this So if I do something like x had 2 k tail 2 k。

And here I have a 2K and a 2K。I think basically what I can do is I can shell and then compare this to the L1 of the previous block and get something like L1 over rootque and I think if I do this properly I can get something like I can prove that this thing will end up being something like。

嗯。Exhale， K。L1 norm over Roquet via shelling。做紧咩。Sorry about that。 Yeah。

 I think I'll fix that in the notes， but you can yeah。

 you can definitely now you can definitely fix this and get an error term that is bounded by this。

 I think you're right it's not going to be it's not going to be bound by this。

 it's going to be bounded by the something like this。这个。I'll fix that in the notes though。

Does that roughly make sense as to what I'm trying to do there？Yeah。

 I think it's similar to dilemma except after you apply pi right， very good。Okay， good， so。So anyway。

 from now on， I'm just going to so I guess maybe it's 2 k。

 but I'll just pretend it's k so from now on x is just x is case parse。

 and then let's run this argument for a caseforax。Okay， so let me do some more definitions。嗯。

So from now on。X is actually sparse。And I'm going to make some definitions， so S star。

I's going to be the support。Of x， so the size of S star is at most k。And then I'm going to say ST。

Is it just defined to be the support of XT？So again。

 this has size at most K as well because we did the hard thresholding operator。And then， Bt。

Is going to be defined to be。S T。Union SR。To the size of B，T。Is that was 2K？

Because I just took the union of two sets each one us has the most。Okay。

 so let's try to understand a bit， let's try and improve a bound now on。The norm of the residual。嗯。

That's what we're after。That's what the theorem is saying about that's founded。Okay， so。

Boing the norm。Good party。So good。We're going to do some triangle inequality。 So R T plus one。

Helsonor。My definition is equal to x minus xt plus1。Which now？ItX is， you know x and x T plus one。

 both of their supports are a subset of Bt plus one， so this is equal to the norm of。Xb T plus one。

I'll just write it like this T plus1 minus Xt plus1。B peoples one。嗯。And then now I'm going to。

I'm going to insert the the vector a before I did the thresholdholding and I'm going to subtract it into triangling inality so this is at most。

X， B， T plus one， Okay， minus8 plus1。B t plus one。Plus。嗯。AB T plus one。Mus x。O。Now。You know。

 what what is I claim that， first of all。This。Oops。I claim that this。Is smaller。Than this。

So the inequality goes something like this。The second cement is smaller than the first cement。

 So why is that。喂。When you apply the hard thresholdholding operator。

 you get the best case spars approximation of the input。😡，So Xt plus one。

Is the hard thresholdholding operator applied applied to A plus1？So meanwhile， X itself。

Remember x is k sparse right from now on we're seeing x is k sparse x is some other K sparse vector。

 so you know it cannot be as good a K sparse approximation to a as xt plus1 is。

So the left suband is bigger， so this is at most two times the left subandd。Does that make sense？

Okay， so now how do we bound that？嗯嗯。😊，Okay， so now let's expand out what a actually means。Okay。

 and from now on。I don't want to keep writing Bt plus1 so from now on。嗯。B。Is Bt plus one。

And be prime。Is BT。Let get it all。 It's confusing。你这。So this is。

So this is two times Xb minus8 plus 10。So let's expand out what A actually means。

OkaySo this is equal to two times。X，b。minus。嗯。Things like X。X TB。then。Minus pi transpose B。

Y minus pi X T。And then now let's also expand out what y means。Why， remember， y is equal to。

Is he equal to pi X plus E？嗯。So。If you expand that out， y is equal to pi explicitly。

 so you have a pi x minus pi X team， that's just equal to pi times r team。

And then you have an E that， you have an E that showed up in there。

 So this is equal to two times X B minus X， B， T。Which， by the way。

 is also known as I guess can write， I can simplify that too。

Xb minus XbT is also known as Rt projected to be， so this is Rt。Project to be。Minus pi b transpose。

 and then y minus pi Xt is equal to also pi Rt。ok。嗯。Plus E。唔姐。For lessons。And now。Good。

 RT is fully supported on B prime。Right， well， actually let me write RT like this。

 I was going to write RT。Is equal to RTB plus。二7。B prime minus B。In reality， oh yeah， you， good。

 I can write that because I know what is what is Rt， Rt is x minus Xt。X has all it supported in。

X has all support neither B or B prime because both of them contain S star。Okay。

 and Xt has all its support and B prime。So be union B prime contains everything， I mean in fact。

 just be Prime does。So now I can write this as， you know， this looks like a mouthful two times RBT。

minus。嗯。Hi B transpose。派比。r tB。Okay。Minus pi B transpose。Pi B prime minus B。

R would be prime minus Bc。Minus。Pi B transpose。一。😊，Does that look great？

So let me move this over to the next slide because this is getting have a lot of symbols。

So we had that and then so what do we start off with Rt plus one？We said at the end of the day。

 it's at most two times。二比七。Okay。Minus。I said pi B transpose， pi B Rt。Minus pi B transpose。

Hi B prime minus B， R T。B prime minus B。And then I think I had a minus pi B transpose E。

So this is the same thing as I'll say identity B。The identity matrix restricted to the columns in B minus pi B transpose pi B。

Times RBT。So I can write it this is all at most。Let let me do trial inequality now。

 two times the operator norm of that matrix。Plus two times the norm of the optum of this matrix。

Times that over the vector。And then plus the operator arm room of this matrix well。嗯。Sure。

Py transfers。嗯。Open this matrix times E。Okay， so I I just did some triang inequalities and I also wrote that the norm of Ax is at most the operator of a times the norm of x。

Okay， does that make sense？So now let's just go through these one by one。Just by definition of RIP。

 okay， remember now this thing， this matrix pi has 3K RIP。Iner。So this thing is at most。Epsilon。

That's just the definition of RIP。Yeah。This thing also。We've used thislema multiple times so far。

 we used it once when we were analyzing basis pursuit。

 we used it once when we were analyzing the Crramer War Theorem for Fast JL。

If you look at pi suba transpose pi B。Wherere A and B。Are disjoint sets？

And their union has size at most。The RIP level of pi， so here pi is 3K RIP。😡。

How big is the union of B and B prime minus B？The union has size at most 3K。

So by alema that we've already seen twice in class so far。This mean。

This thing has operated room at most epsilon。And if you don't remember the intuition for that。

We basically used the parallelogram rule， we said， look。Let's say that you have two column。

 two sets of columns A and B， which are completely disjoint。Okay， and let's say x is fully， you know。

 let's let me give two different letters， let's say that we have vectors y and Z Y is fully supported in A。

Z is fully supported in B。Why do Z is zero？Right。So pi y times pis Z or pi y dot pis Z should be close to zero。

By parallelogram rule， as long as pi preserves the norm of y plus z and y minus Z。

 you can do some parallelogram rule and expand and cancel similar terms and you'll get the dot product has to be preserved up to additive error epsilon the original error was zero so the new error has to be at most epsilon I mean not error。

 the original dot product was zero because they have disjoint support so the new dot product has to be at most epsilon。

Which implies that the operator norm of pi a transpose pi B is at most epsilon。

So as long as the sets are disjoint support and the total union has sized at most the RIP level of the matrix pi。

 they're good to go and the operator is going steps line， which is true for us。

So this matrixes operator almost epsilon。And also， again。

Pi B pi B transpose pi B is close to the identity and operator norm。

 It's with an epsilon of the identity and operator norm。 What does that mean It means that。

All the singular values。Of pi B transpose pi B。Are between one minus epsilon and one plus epsilon。

So if you know that all the singular values of pi B transpose pi B are between one minus epsilon and one plus epsilon。

What does that say about the singular values of pi B transpose well， first of all。

 they're the same as the singular values of pi B。What are the singular rounds of Pi B？

What are the if I tell you the singular values of a transpose a？

What are the singular values of a in terms of the singular values of a transpose a？Yes。Square root。

 Yeah， they're just a square root。So you know that pi B transpose pi B。

Has all its singular values between 1 minus epsilon and1 plus epsilon。

 So that tells you that the singular values of pi B transpose have to be between。

Route  one minus epsilon and root one plus epsilon。So in other words， they're still close to one。

So in summary， this whole thing is at most。To epsilon。I think there's also a two out here too。

 I forgot the two。嗯。Two times。Yeah， so it's right two time， two epsilon。RBT。L twoor。Plus。

RB prime minus B。知。Llseor。对。Plus two times the square root of1 plus epsil and times it R E。

Which you know that this is， this is anyway now I can ignore this this is， yeah。

 so this is at most let's say three times in order to eat， I'll be able to sloppy。

As long as Upilon is small enough。Okay， what can I say about this？

So this is just a this is again this is going to be like the AMGM inequality So notice that like let's just call this。

Let is give these names， this's called this alphapha。Now let's call this beta。喂。

What do I know alpha squared plus beta squared in this case is equal to because they have district support this equal to。

R B prime T。Elitude normm squared。Right。Because it's equal to RB squared plus Rb prime minus b squared。

 but those are district support， so the squared norms just sum up。Okay， so let's just call this。

 let's just call this， yeah， so again， so good， it's something。

But we don't have alpha squared plus beta squared， we have alpha plus beta。

So what can I say about alpha pluss beta？I claim， I claim that。This is a fact about numbers。

Alpha plus beta， I claim is at most。嗯。Square root of two times alpha squared plus beta squared。

So okay， so in other words。In other words， if you look at the sum。

What I'm saying is that this thing is at most square root2 times the norm of R B prime T。

 so why is this fact true， you just square both sides。

So this is the same thing as saying alpha squared plus2 alpha beta。

So this is the same thing as saying， but this is true。

 Al square plus alpha beta plus beta squared is at most two alpha squared plus2 beta squared。

Which is the same thing as saying that。Alpha beta is at most alpha squared plus beta squared over two if you just rearrange things。

But this is true by the AMGM inequality。My arithmetic mean is that。I was it going the wrong way。嗯。

Yeah， the arithmetic mean is at least the geometric mean。

So the arithmetic mean between a squared and b squared is at least the geometric mean between a squared and b squared。

 which is AB or alpha beta。对。So， in summary。What we have is that。R T plus 1 L2 norm。Up there。

Is that most？嗯。Two epsilon。Times or two epsilon。Because there's a root two there now。

 two root two epsilon times R B prime。7。Ll2or plus。Three times an over E。And remember what I said。

 I said that epsilon is small， epsilon is less than one over four root two。Right。

That was my condition。N see why。So now if I go back to where I was。And use that fact。This is at most。

One half times the norm of R T。B prime L2 arm。Plus， three times the2。And by the way。

R RTB prime is also known as。RRT。You don't need to be prime there， right because what is Rt。

 Rt is x minus xt。Right， so。X has its support contained in B prime by definition， by definition。

 B prime contains S star。Right。B prime is just BT， which contains S star。

And B prime also contains ST。So it contains the support of Xt as well。

 so Rt is fully supported in B prime so I can just drop the B prime。Okay。

 so we're getting some kind of exponential decay。RRT plus one。

Has norm at most half of R T plus three times E times L2 norm。 So what you can show so you know。

 if you can do this out formally by induction if you want， but basically what you're getting is that。

嗯。The claim can prove by induction。So， you know， if you just look one level deeper。嗯。

So you know that。So what do you know， you know that R zero。Has an norm。Equal actually。

 because our our x0 is just the zero vector。 So this equals the norm of x。Meanwhile， R1。

We said is that most？A half times the norm of x。Plus now three times E2。Let's just do one more。

 so what about the neuro R2？This thing is umost。A quarter times the norm of x。

Plus3 hals times the norm of E2。Plus three times it over be2。So， you know。Eventually。

 we're going to is to get RT。Is gonna be like。At most。

 the norm of Rt is going to be at most1 over two to the t times the norm of x。Plus。

Three times zero one plus a half plus a quarter plus whatever。Times the over E。Yeah。

So what you're going to get is。R T plus one。Is actually that most something like1 over2 to the t plus 1 times the number of x。

Plus， you know， at most， something like six times the need。And remember。This E was really。Yeah。

 each though。So when you bound that norm Eilda， that's when you get， you know。

 the dependence on like whatever root k times the norm of X k。谁？So that's pretty much it。

Questions about this analysis。Any questions？Okay so if there are no questions we still have 15 minutes left so I'm going to do is i'm not going to do a full analysis。

 but i'll tell you about you know another kind of very different way of coming up with measurement matrices that also gives you some kind of decent recovery results and it's based on the notion of an expander so just out of curiosity who here。

In the audience knows about expanders。Anyone。Yeah， I think a few of us are thumbsing up in the okay。

 sorry， I can't see the chat so。T your one second。I saw two thumbs ups。

 but I don't know if I saw all of them。Okay。Yeah sorry。Three thumbs ups Oh okay good。2。

So first of all。Another method。For compressed sensing。

And there are also iterative recovery algorithms。That corresponded this method。

So instead of choosing pi to be like a random Gaussian matrix or something。

 what we're going to do is we're going to pick pi to be the adjacency matrix of an unbalanced Hyid expander。

Okay。So expanders。I'm going to specifically talk about biid expanders。嗯。

So what we're going to do is we're going to have。It's going to be imbalance。

 so here we're going to have a vertices。And here we're going to have M vertices。

Hinent M is going to be the number of measurements in our matrix。

 and n is going to be the coordinates。It's called this V。

And we're going to have a left regular graph that's d left regular。

 so every vertex here has out degree exactly D。So G is equal to UVE， it's bipartheid。And it's D。

Left regular or left deregular， I don't know， but the order to save those things in。

So what does it mean to be an expander so we're looking at so called lossless expanders okay。嗯。

If you look at， let's say gam is the neighborhood function。Check。😊，S。

 which is a subset of the left side。And look at gamma of S。

So gamma S is the set of all things which are neighbors on the right。空间。Now。

What's the biggest this could possibly be？ the biggest this could possibly be is that os。

Is that most？D times the size of S。Right if single if every single edge coming out of S。

 there are no collisions， they all go to different vertices on the right。

The most you could possibly get is d times S。If it gets at least one minus epsilon times d times S。嗯。

It gets this。For all。Subsets S of U subset the size of S is at most k。Then， we call G。And。

let's call it a K epsilon D expander。So that's the definition of a apartheid expander for those of you who have not seen expanders before。

You mean you can also talk about。It does， you know， you can make the same definition for。嗯。

For for non bipartite expanders as well， basically if you take any subset of vertices。

 you just want to say that if you look at its neighborhood， it expands a lot。Okay， so for example。

 you know， something that would not be an expander。Would be。A bad example。Would be something like。

This is the canonical that example what's called a barbell graph so imagine that。

Imagine that these are like very tightly connected graphs。But there's like one very loose。Is that。

 is that what I want to say， actually， you know， let me just draw， you know， let me not be to。Fancy。

 here's， here's， here's okay。 Here's a very simple bad example。 Okay。

 so a very simple bad example is。So let me just let me just divide up the right hand vertices V into like three groups of size three。

And let's say that。嗯。Each vertex on the left is connected to one guy in each bubble on the right。

 so like this is this is all the。And this is you。And let's say this guy's connected here。

Here and here。What I don't want to happen is I don't want this guy to also， let's say。

 go to the same exact places。And maybe the next guy also does that。

This would not be an expander because if you look at a small subset on the left。

Like if you just look at these two vertices， for example。You you want that， you know。

 the maximum verses on the right they can hit is six because each one hits three and if they're disjoint。

 they'll hit six， but here the union of what they're hitting is only three because they overlap too much。

So an expander is a graph where that doesn't happen if you take any subset of vertices on the left。

They don't overlap too much in terms of who they hit。

 there can be some overlap because that's why you have that epsilon loss there。

But it shouldn't be too much of。Okay， so now you can show that。

You can show that good expanders exist。Dorem。There exists expanders。What parameters。嗯。You know。

 what's that call it K， epsilon D？For and being something like。

O of k over Epsilon squared log n over k。And D being of1 over epsilon squared login。Yeah。

And the proof is the probil of nothing。So again， you just take your in vertices on the left。

And then what you do on the right is。You just break up。For this setting of parameters。

 you just break up the right hand side into little sublobs。Where you have。D sublos。Each with。

M over D vertices。And then you just pick a totally random graph， each guy， each guy on the left。

Has one neighbor chosen at random in each sublo， so one random neighbor here。

 one random neighbor here， one random neighbor here， same thing here， one random neighbor here。

 one random neighbor here， random neighbor here。And then you just prove that it has the property you want with high probability。

Byu a union bound， you look at all possible subs on the left of size K or and choose K of them。

You say with high probability this subset doesn't have too much overlap if things are random and then you union bound over all of them okay so that's in terms of existence。

 people don't know how to construct such a graph deterministically that has this property okay we just we just know that you we can pick them we know we know how to get graphs like that have that property randomly by just randomly picking a graph it'll have it with high probability although we don't know how to check that it has it we just hope that it has it because it does with high probability。

But if you want to deterministic construction， that's a major open problem in pseudo randomdomness is like constructing。

Constructing an explicit expander graph that has such good parameters， we don't know how to do that。

Okay。Okay good， so that's what an expander is， so what does that have to do with us？Dearem。嗯。If拍。

Is the adjacency matrix？Of an expander。With parameters。Let's say， specifically。With。

 you know K being like， oh， of the sparssity。Soorry， i guess i read i i啊。

The K that you're going to choose in the definition of expander is going to be like。

 oh of the K that you used for sparsity。Can recover。It told that from Pax。

Such that you're going to get you're not going to get L2 L1 guarantee。

 you're going to get something like an L1 L1 guarantee such that。

X minus x tilde1 norm is at most big O of。One， so some constant times。X条K。

So you got an L1 L1 guarantee and in fact， it's possible。

Possible to make this be even like one plus epsilon and that was due to。嗯。Indi con。In 2008。

This is an iterative algorithm。And in fact， achieve you can even achieve this thing here with basis pursuit。

But again， there are also itative algorithms that make it faster。

That'll cost to the seven basis percent。3。So mean， we only have five minutes left。

 so I'm not going to show you the proof of this。But it's just， you know。

 it's a totally different way， it looks very different from what we've been talking about before in terms of what do we say said。

You can get an RIP matrix using JL， you can get it from sparse from fast JL。

 you can get it from incoherent matrices， so this is just totally different and in fact。

The adjacency matrix of an expander is not actually going to be RIP in the definition that I gave you earlier。

It's it's going to be what's called RP1 RP1 means。😡。

I preserve the norm the L1 norm of any case bar vector as opposed to the L2 norm。

So you can show that you can show that the adjacency matrix of an expander with the right parameters satisfies RP1。

 it preserves the L1 norm of case bar vectors and you can also show the converse you can show that。

If you have。A  zero1 matrix。That satisfies RIP1 and by the way。

 you should in order to get RIP1 you have to normalize by the degree。

 but it's some universal normalizing constant。😡，On the flip side。

 if you have a matrix where all the entries are either zero or the same positive number。

 like one over D， you can show that。😡，If it has REP1， it must be。

 you know it must represent the adjacency matrix of an expander， so these are equivalent notions。😡。

Unfortunately。You actually can't prove black box that R1 implies basis pursuit works that's actually false you can come up with a counter example of a matrix that has R1。

😡，But X basis pursuit doesn't work with that matrix this is an example of Michael Cohen from a few years ago。

But if you use the fact that if you open the abstraction and say not only is it RP1。

 but it's the adjacency matrix of an expander， you can use that property to analyze basis pursuit and argue that it gives you this kind of guarantee that I circled in red。

O。Any other questions？O。And yeah， I guess and maybe just one last thing I'll leave you with this is unrelated。

 but for the many of you who said you hadn't heard of expand before。嗯。Exp。

 I mean an intuitive way to think about these are combinatorial expanders。

 there's also something called spectral expanders but they're actually related via something called Gers inequ。

But the thing to have in mind when someone talks about expanders。

Is you basically an expander is a graph that doesn't have any sparse cuts， what do I mean by that？

So you can define the sparsity of a cut。Or the conductance， let's say， the conductance of a cut。

Let's call it phi phi in the graph of S， the definition of that。

Is just this is it's called the boundary of S。嗯。Divided by the minimum。

Of the volume of S and the volume of S bar。So what does this mean？

The volume of a set is just defined to be the sub over x in a of the degree of x。So what it's saying。

 so you know expanders。Exps are graphs。Where。Phi of S。Is large。For all。嗯。Smallness。

So what you don't want to have is。You don't want to have a situation where。

So let's let's look at graph， know， let's look at some big graph。Let's cut off a small piece。

So right， there are some edges here。There's some edges here。

There are also some edges that cross the boundary。So the edge is that cross the boundary。Okay。

Let's say this is S。And this is Sbar。So imagine that s is the smaller side of the cut， right。

 meaning that。嗯。If you look at the min。If like the min here， S is the smaller side。

 so the Va S has fewer edges that are that are incident upon S。So what it's saying is。

The majority of the edges that are incident upon S are actually the yellow edges。

 It's to be an expander， Exper means。Means that there are few。Black edges。On the S side。Of the cut。

Most。Edges。On the S side。Or yellow。Okay that means most of the edges actually leave us。

 they don't stay inside us。对。It's to it's related to spectral considerations because it's also related to the mixing time of random walks。

So， for example。Imagine that。You imaginemag that you're in a situation where here's S。

There's a lot of edges in here and it has one edge that leaves it。So of a much bigger region。

Imagine that you did a random walk。In the graph that started at some vertex in S。

It's probably going to get stuck following all these black edges for a while before it finally crosses over this yellow edge。

So we say that kind of that that cut， that cut right here that separates S from S bar is an impediment to the random walk mixing quickly。

So you want to say that no there are no such impediments。

 there are no cuts that are very sparse that have very few edges crossing the cut。If that happens。

 it's not good， it doesn't random walks don't mix quickly。Does that mean， that's another。

That's another。So you know， related definition to expanders that's's that's the definition of what's called a spectral expander。

 which you can show as a connection to the definition that we talked about。Anyway。

 that's enough of an aside， I think we're definitely out of time now any any let me stop recording。

And ask， are there any final questions？

![](img/bc7e99ef8906c34030902c1f6d789240_2.png)