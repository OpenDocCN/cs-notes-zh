# 信息论、模式识别和神经网络The Information Theory Pattern Recognition and Neural Networks 2014 - P9：-09-Lecture 9_ A Noisy Channel Coding Gem, And An Introduction To Bayesian Infer - GPT中英字幕课程资源 - BV1er421M7Br

![](img/6bf61dddb98a7d46459efd00543906ad_0.png)

Okay， welcome to lecture number 9。 Today， our main topic is going to be inference inferring parameters。

 For example， you do a science experiment and you want to infer the parameters that underlie the data you've got。

 But before we do that， I want to point out to you a little gem of information theory that you may not have noticed。

I'd like us to start by thinking about the binary erasure channel。

 What we did in the last couple of lectures was we established Shannon's noisy channel coding theorem that says for any channel。

 you can work out its capacity by maximizing mutual information。😊。

And then it's possible to make an encoder and a decoder that communicate reliably over that channel。

Reliably， meaning you can get the error probability as close as you like to 0。

 but you can always communicate at any rate up to the capacity。

So what's the capacity of the binary eraia channel， Please have a quick chat to your neighbor。

Here's a question， and I'll go solve it over here in just one minute。



![](img/6bf61dddb98a7d46459efd00543906ad_2.png)

![](img/6bf61dddb98a7d46459efd00543906ad_3.png)

So there's always two ways you can solve these questions。You can either。

Work out the mutual information this way around。哦。You can work it out this way around。And often。

 one way is easier than the other。So， let's do the。Boary erasia channel both ways round。

 I'll generalize a little bit。So that we're putting in。



![](img/6bf61dddb98a7d46459efd00543906ad_5.png)

P0 and P 1， because I'll pretend we don't know that the optimal optimal input distribution。

 of course， has to be symmetric。And I'll call these proities。F and1 minus F。So if we do it this way。

 the first term is binary entropy of p。

![](img/6bf61dddb98a7d46459efd00543906ad_7.png)

And then the second term， we need to think through all the different whys that could happen。

 That's quite a lot of work。 We need to think about three things。 Figure out how probable they are。

 Then work out what the entropy of X given Y is。 That's quite a lot of work。

 Except almost all of it is easy。 If you get a 0， you know that the input was a 0， so。

There's no entropy in that case。Similarly， if the output is a w。

Then the input doesn't have any entropy anymore。 It's only if the question mark comes out。

 which happens with probability F。M by hook or by crook。Then you still don't know what the input was。

 And you've got no information at all about what the input was。

 The posterior distribution of the input is still the same as it was when we started， so。

A should be not。Which is。8 to a peanut。Time's 1 minus f。We maximize that with respect to P n。

You end up with P equals a half。Whi gives you warm times。我王云帅。Okay。

So usually doing it this way round is a bit hard because you have to think about lots of inferences。

 But in this case， those three inferences were fairly easy So this was a nice route。For solving this。

Alternatively， we could have worked out the entropy of why。

 That means you need to work out the entropy of the probability of why。Being0。

Why being question mark。And why being。1， and you could laborly work out those three numbers。

 The probability of getting a0 out is。The probability that you put in a 0， multiplied by。1 minus f。

Et cetera。 So you could work out those three numbers。

 Then you have a big mass of stuff to put into the entropy computation。

 You have to do P log1 over P plus P U log 1 over P three terms。

 So that looks like a terrible load of work。Then secondly， we want the entropy of Y given X。

 That's easier because if you condition on a particular X going in， then the entropy of y is， well。

 it's just a choice between 0 or question mark。 or one online question mark。

 And the entropy of that distribution is the same either way round is just H2。Of F。

 So that was an easy thing。 This is looking horrendous。

 But I want to introduce you to a little property of the entropy。

 which we call the decomposability of the entropy。This is not the gem。 Sorry。

 we're getting to the gym in a moment。The decomposability of the entropy says you can， if you want。

 work out the entropy of a distribution over several characters in an alphabet。

By imagining that you learn the character in a sequence of steps and add up how much entropy you get。

 on average at each of those steps。 So first， you could imagine finding out is。😊。

The character that came out a question mark or not。

 And we know that the fraction of question marks coming out is always F。

 Does't matter what input distribution you go for。So we can say， first。Was it a question mark。

 And then。If not。What was it。And then， the en of y。

Is the sum of the amount of entropy you get at each of those steps。 So first。

 you get the entropy of F。For finding out， is it a question mark or something else。Then。

With probability 1 minus F， it's something else。And then you get the entropy。

Of finding out whether it's a 0 or 1， given that， you know that it's not a question mark and the probability of 0 or  one。

 if you know it's not a question mark that's come out， is just the same as P nm P 1。

 It's the same ratio。 So the entry of that。Is。H2 F P not。Okay， so that's。In the textbook as well。

 if you want to read up and。Clarify what I just told you。

 you can make life easy for yourself by being smart about how you compute enpiece。

 So this was looking hairy， but it's not too hairy when we do it that way。

 And so the answer comes out to be mutual information。Is equal to this lot， which is H O F plus room。

He， to。Plus 1-。And write to note。Minus this thing， which is H to F。

And we have a grand cancellation of H2s of F。And we're left with one F H2 P note， as we had before。

 when you maximize that， the capacity。What this should have said capacity is or minus F。Okay。

So we found out the capacity。Now， I want to go back to this diagram。

 Everything we talked about in noisy channel coding said， let's imagine we've got a noisy channel。

 and we're going to slap a clever encoder on the front that adds redundancy。

 And we're going to add a clever decoder that does inference to infer what the input was。😊。

How fast can we communicate， And we worked that out， and we solve the noise channel coding theorem。

 And for this particular channel， the answer is you can communicate at a rate。😊。

1 minus F with essentially0 errors。That's achievable。那。

Imagine that we had introduced a completely different topic， called。Noy channel coding with feedback。

 So I'm gonna change this diagram now。 And I'm gonna imagine a completely different diagram where everything that comes out of the channel。

😊，Gets back。And is available。To the encoder， right， that's a different diagram。

He's got an extra communication link。Back from the end of the channel to the encoder。

 So the encoder knows exactly what's going on。So if the encoder sends， for example，1，0，0，1，0，1，1，1。

And what comes out of the channel might have some question marks in it，1，0，0 question mark 0。

OneOne question mark。啊。What's the answer to the question。

 How fast can you communicate over this channel， given that you've got feedback available to you。

 that might completely change the game， right。Because the sort of encoding trick you could now use is you could just say。

 well， I'm gonna listen to my output。 And whenever there's a question mark。

 I will retransmit the thing that was just lost because I know that they didn't receive anything。

So I'll just retransmit。 So you wouldn't use。This story here， If you heard the question mark。

 you're trying to send one bomb。 What you would send would be。嗯。So this is your original source。

And then， your transmission。Would be assuming that a question mark happened at the fourth and。Okay。

 what would you transmit， You would transmit。1，0，0，1。

 Then you transmit the one again because the question mark happened。 Then you'd keep on going 0，1。

 and then。That's the8 thing here。 The next one is a one， but that gets lost。

 There's another question mark here。And so， you transmitted again。I think when I say it in words。

 it's clearer than when I draw it on the board。Okay， you keep them。

Transmitting a symbol until it is correctly received。

What's the rate you're going to be able to achieve with that clever scheme that's making use of this feedback。

 Have a chat to your neighbor。

![](img/6bf61dddb98a7d46459efd00543906ad_9.png)

Anyone， what rate can you communicate at。If you make use of the red feedback link。On average。Anyone。

So。If you just imagine how much of the time you spend successfully communicating。

 it's whenever there aren't question marks， you have got another bit over the channel。

 When there's a question mark coming out， you aren't achieving reliable communication at all。😊。

And the fraction of time that there are question mark is F。

So the rate at which you're communicating using this feedback link is。我完晒。Any questions， anyone。

Not clear on this。Yes， so。Whenever if there are several question marks in a row。

 you just keep on retransmitting until what comes out of the channel is not a question mark。收。

Retransmitting。Doesn't affect this argument。 The argument is， if this is time。And if you send。Sybols。

 and if some of them get turned into question marks。

Then you're gonna be successfully communicating in all of these。Instance here。

Whether or not question marks。Every time there's not a question mark。

 you will have got the next bit across。So it's not relevant whether the question marks clustered together Every time there isnt the question mark。

 the next bit will have been transmitted。 And you just move on to the next one in the file。Alright。

So when you use feedback， you are communicating on average at a rate 1 minus F。

1 minus f bits per unit of time per。Use of the channel。Oh my goodness。 That's the same。Was this。

So we added feedback， which made life much easier for us。

 but it hasn't actually increased the rate at which we can communicate。 So here's Claude Channon。

 now， sadly deceased。And Shannon is saying。Should we redo all of information theory to include feedback。

 And the answer is， no， Pa， you don't need feedback。 Just use a random code。

 Just use a really smart random encoder， an appropriate decoder。 And you don't need feedback。

 Feback doesn't actually help you communicate any faster。 So that's a gem for me。😊。



![](img/6bf61dddb98a7d46459efd00543906ad_11.png)

And there are erasia correcting codes called fountain codes that allow you to communicate almost at the capacity of erassure channels。

 And fountain codes are in Chapt 50 of the textbook。Any questions？Gus。Okay， so Gos's question is。

 what if you had errors in the feedback channel sometimes， then what would you do。

 And Channon would say， I'm not gonna use the feedback anyway because it's not helping。 So， yes。

 you pointed out it could make things worse if you trusted the feedback and it wasn't trustworthy。

But， we don't need it。So，Okay。On with the show。Let's now talk about inference。 And I'm going to。

 in this lecture， look at。

![](img/6bf61dddb98a7d46459efd00543906ad_13.png)

A very simple inference problem。

![](img/6bf61dddb98a7d46459efd00543906ad_15.png)

People often work with Gaussian distributions， and we'll look at the Gaussian distribution for this lecture。

 But I will rapidly move us on to other more interesting distributions， because。For Gaussians。

 it doesn't really change your life to say， now I'm gonna learn how to do inference right because the standard methods of dealing with Gaussians are already fine。

 But I'm gonna to point out to you in the next lecture， that when you look at other problems。

 apart from inferring the mean and standard deviation of Gaussian。

 it can transform your life when you learn how to actually do things right instead of using ad hoies。

😊，S。The general topic we're discussing now is inference。

And the sort of motivations we might have for doing inference are， maybe we're doing。Cosmology。

And there are some unknown cosmological parameters。And we use some nice， big。

 expensive telescopes and satellites and things。 And those underlying cosmological parameters like Hubble constants and the amounts of dark matter and this and that give rise to cosmic micro background radiation fluctuations。

😊，And you measure those。 So you get some measurements。Of them， imperfect， noisy measurements。

And maybe you observe supernovae， as well。Oops， that should have gone here。

 They're caused by the same cosmology， and you measure。Properties of your supernovae。

 And then having made all of those measurements。We want to infer， okay， what do we believe about。

The Hubble constant。 We want to infer。All of those cosmological parameters。Here's another motivation。

 Maybe you still use email。And when you receive emails， here's email  warm， email to and so forth。

There is an underlying variable that you might care about， which is。

 was it actually a piece of spam or not， so。This is a variable called whether this particular item is spam。

 And then E1 to pop pop dot are the actual emails that come out and to save your time。



![](img/6bf61dddb98a7d46459efd00543906ad_17.png)

To save the almost infinite amounts of time that you might need to delete the spam yourself。

 you'd like to have an automated method of just looking at the email and inferring this spam variable。

So you might want a spam filter。What's some other examples well。

We might be wanting to do image recognition， speech recognition， character recognition。呃。

Amage direct。Speech rack。Character recognition for printed or handwritten characters。

And the general pattern is。There's something on the left hand side。

 which is the underlying message or thing we care about。

 And what comes out on the right is some sort of data that depends on that。

 We want to turn the arrow around and infer the thing。On the left hand side， the underlying causes。

Okay。Just going back to spam example。The sort of way you might imagine handling spam is。

 you might imagine。Emails living in a space of email and real emails to you that you do want to read might actually fall into clusters emails about wind power。

 emails about。Baesian inference。Hes about ultimate Frisbee。

 So you've got all the non spm spam clusters。 And then you've got spam about。

Russian this and Nigeria and that and， and so forth。And different colours of pills。And we want to。

Infer these clusters， and。I reliably identify the stuff in the clusters that we do care about。

So you could think of spammer as maybe being a clustering problem。

 And we'll talk a bit about clustering。AndNext time or the time after。

So given that we're gonna talk about clusters。And given how prevalent。

The use of Gaussian distributions is。Let's chat a little bit about a toy problem。

Where what's going on is there's a mean and there's a standard deviation and out popps some data。X 1。

Through。X and。My notation that I'll try and use consistently is in general。

 N is gonna be the amount of data we get。 Little N is always going run from one to n。

 So whenever you see a suffix， you can usually infer what it goes up to without me saying so anymore。

 And I try to use the same letter fairly consistently。Alright， and this is a Gasian distribution。

 So to be completely explicit， P of X， N given mu and sigma。Heres。

One over a square root of two pi ciig squared。E minus。Minus new。Squared over。To sigma squared。

 And this has little x。And。H it， okay， and the task is， we want to infer mu and sigma。Given them。A代。

Right。Let's do that。

![](img/6bf61dddb98a7d46459efd00543906ad_19.png)

So let's walk through the world that we are working in。

And it's good to always distinguish two worlds。 One is hypothesis space where parameters live。

And another is the world in which data lives。 And in this case， confusingly。

 they both look kind of similar to each other because the unknown mean could be anywhere on the real line。

 and the data come on the real line。 But I'll try to keep track of when we're talking about a data axis。

 labeled X。 and when are we talking about。A hypothesis axis that might be labeled mu。

All of the data points come along this data axis。 The， the。

 the hypothesis space actually has two dimensions to it。 It's got a sigma。Dimension to it as well。

 So one way of telling the difference is sometimes we'll show a mu axis and a sigma axis。

 And if you see two dimensions， we must be in the hypothesis space， the parameter space。

So here's a one dimensional picture， and it shows for six possible different settings of mu and sigma。

 all of which happen to have the same value of sigma。 What the prediction about the data would be。

 So these are standard Gaussian densities for different values of mu and sigma。😊。

These all happen to have different values of mu and the same value of Sigma， namely Sigma is one。

Okay， next。Here are another six possible hypotheses about mu and Sigma， where。

The muse all happened to be the same， and the standard deviations vary from 。5 up to 2。

 So what did I do there， I just toddled around in the hypothesis space。And showed you 1，2。

3 for5 6 points in this two dimensional space here。

 Maybe I'll quickly get rid of data space for a moment。So I showed you six hypotheses like that。

And then。6 hypothees。Like this。 So I toddled along the U axis and along the Sigma axis showing you in data space what each of those predicts。

 So any particular one of these makes its own prediction in the data space， which looks。Like that。

 It says that's what I'd expect the data to be like， if I am true。Okay。

 and here are another six hypotheses， which have different muse and different sigmas from each other。

 So that's， that's a scattering of points。In mu and sigma space。 And for each one of them。

 I've shown its predictions in。Data space。Okay。So。How do we do inference。We want to in mu and Sigma。

 This is the correct way to do inference。 You get your data here I'm showing。

 we want to give for five data points which have arrived at these horizontal coordinates here。

 I've just slapped them above the line。At an arbitrary Y coordinate。Right。

 so we've got five data points。 What does base theorem say you should do Well， you should update。

Your beliefs。About mu and sigma in proportion to how well each of those values of mu and sigma predicted what actually happened。

So。B theorem says， how probable mu and sigma are given the data。Is。How well they predicted the data。

Multiply by how probable they were。Before you got the data。Normalized。It's normalizing constant。I。

Inteeggo。这名。D sigma。Of the stuff upstairs。No。I'm taking for the next few lectures。

 quitete a hard line position that I think when there's a well posed question。

 there's a correct answer to it。 And this is in contrast to the way a lot of people think about statistical inference。

 There's another way of doing inference where there's lots of ways of answering well pose questions。

 And I think that's an extraordinary thing to believe。 I think there is。

A correct way of answering well pose problems。 And I don't think inference should be an exception from this。

Something to make really explicit is that。All these inferences depend on assumptions。

So people sometimes say， oh， baesian methods。 They're so subjective。

 They depend on assumptions as if you don't have to make assumptions in order to do inference and。

I forgot to write， yes， these all depend on assumptions。But how could it be otherwise。

 So every one of these things is condition on H。And this。And is this。And so is this。

 And H is the assumption that the data come from a Gas distribution。

 And it's whatever assumptions we want to make about what we believe Mu and Sigma might be beforehand。

 And I think it's un unescapable that you do have to make those sort of assumptions。All right。

So what does this actually look like， Well， this is saying。

 how well did you predict the data that actually happened。 And this is the， the meat of it。You know。

 if we， if we haven't got any particular strong， interesting prior knowledge about mu and Sigma。

 wed better go and focus on the data dependent term。And B theorem says。

 you don't need to know how well they were predicting things that didn't happen。

 Ta probabilities are not relevant。 There's no such thing as tails in the correct way of doing inference。

All you need to do is look at the values of these predictive densities at the five data values that have actually occurred。

 So if we wanted to compare just these six hypotheses that I've identified on the screen by the。

 the rainbow of six different colour。The only numbers you need to know to answer that question are the numbers highlighted by these points here。

 which are the probability density assigned to the data that actually happened by those six different hypotheses。

 Of course， the full phase of hypotheses is the infinite space of all possible values of mu and sigma。

😊，But if we just wanted to compare these 6， that's what you need to know What you do with them Well you work them out and you multiply them together。

 because the probability of all the data， if you assume that the data are coming independently from a Gaussian。

 this thing upstairs here， this is just the product from one to end。Of here that。Given me and sigma。

 which we already wrote down。Over here， So we just need to multiply those numbers together。

And that gives us the likelihood， which is how well you predicted what actually happened。Okay。

So those numbers are all that is relevant to the inference。So what does that look like。

 What does one of those numbers look like， I'm going to。

Reduce the size of the data set down from 5 to just one。

And now I'm going to wander around the hypothesis space， new sigma， looking at what happens to。



![](img/6bf61dddb98a7d46459efd00543906ad_21.png)

The value of P of X， N。Given Mu and sigma， as we wander around in mu and sigma space。

 And this is what it looks like。 So I'm going to slide across a fixed Sigma。

 And then different values of fixed Sigma toddle through。 So here's an example。

 Here's a value of mu and sigma。 And I've drawn a little spike here。

 whose length is the same as the height from the Y axis to the yellow curve there。 alright。😊。



![](img/6bf61dddb98a7d46459efd00543906ad_23.png)

And we're going to wander around adding spikes systematically。 So let's go total， Toddle， To， To， To。

 total。And hopefully， you can see these with thin lines that show how high the orange star was above the way axis for each of those possible values of view and sigma。

And it's not very surprising that what that looks like is a Gaussian with the same width as the standard deviation we just picked。

 which was 1。2 as I toddled through those new values。 Let's switch to another value of sigma。

 This is a smaller value。 We go toddle。 and there's a load of blue things showing how well those hypotheses predicted this same data pipe。

 And we keep on going。 a little du。 This is a skinnier one。 It's higher at the peak。

 So we get an even higher spike in purple。😊，And。We can make a surface plot of what all of those look like。

And here they are for any particular fixed value sigma， It looks like a bump that goes up and down。

 and it's Gaussian in shape。As you come to smaller and smaller values。

 the height of that Gaussian is getting higher and higher。

 So the contour plot is actually a slightly scary looking thing there。So， for a single term。

Let's do a bit more wiping。You。Sigma， a contour plot。As conours。

That looks something like that with these being hypotheses down here with extremely small values of sigma that just happened to nail the data really precisely。

 So that's the likelihood function。In the case of one data point。

 showing how well every possible value from you in Sigma predicted what happened。Okay。Now。

 let's repeat that。 And now we'll multiply together five of those things。

 So we're gonna look at the product for five of these functions， if you like。

 as you wander around immune sigma space。 And it's for these five data points。😊。

So when you take the five numbers shown there。And multiply them all together。

The product is this little orange stick shown on the right hand side。So off go。

 multiply all those together。 You get a very small number。 Multiply those。 you get a small number。

 get a bigger number， bigger， and then smaller again。Right， change sigma to a smaller value。

 multiply them together。 and it went up and it came down。

 And because we're multiplying as we these scans across。

 we're multiplying things that are Gaussian functions with each other。

 though the Gaussians are centered on different values， the product of all those is still a Gaussian。

 in fact， So every one of these little humps we're tracing out is still a Gaussian。😊。

And that one managed to be higher。 This one with sigma。

 as we went across looking at values of sigma equals 0 。6。 We got a higher peak。

 And now we try sigma is0 。5。 And in， we find oh， an even higher peak。

 But now if we go to an even smaller value， Sigma is。Roughly a quarter。Now。

 when you multiply together， these five。Purple numbers。Some of them are quite close to 0。

 And so we're not doing quite so well anymore。 So as we made the red scan there。

 maybe it's a bit hard to see the red scan， the highest it got to isn't as high as。Mr。 Purple there。

 Okay， so what has happened。Now， if we do a cont plot of the product。This was for just one data。

They make a front point plot for five data points of the likelihood。He of。Ex and given you and sigma。

It looks like this。It looks。A bit like that。So it's unimmodal， and it doesn't have a scary。

 bizarre place where infinities happen than here anymore。Alright， and we can ask the question。

 what is the best hypothesis in the sense of the hypothesis that had the highest likelihood。



![](img/6bf61dddb98a7d46459efd00543906ad_25.png)

So this point here。Not that it's got any special status at all。 It， it's not an essential thing to。嗯。

To focus on， but people sometimes do。You can go find the new and the sigma that have the highest likelihood。

 And it's a simple homework exercise to work out the formula for that， if you want。And。

The maximum likelihood parameters are shown there for this data。

 and the green line is showing what the predictive density looks like when you set mu in sigma to those values。



![](img/6bf61dddb98a7d46459efd00543906ad_27.png)

Right， so。Once you've got a likelihood， you can， if you want。

 go and find the parameters that have the biggest value of the likelihood function。As I said。

 that's not fundamental。 The fundamental thing you want to do when you're doing inference is you want to know the whole posterior distribution。

Not just。The setting of new new sigma that happened to maximize this thing。Rightright。

 so that's the maximum likelihood parameters。 And going back to the entire likelihood function。

 this is what it looks like when we spin it round。So I've shown it as a contour plot on the bottom。

 and up up above is a log scale surface plot。Right。



![](img/6bf61dddb98a7d46459efd00543906ad_29.png)

So if you do the homework exercise and you work out what the maximum likelihood value of mu and sigma is。

You may not be surprised to find that。New maximum likelihood。Is。X bar。 And indeed。

 as you slide across for any。Possible value of sigma。

 the maximum value of the likelihood or any slicing value of sigma is at the dateta mean X bar being by definitions of n goes from one to n。

 X， N over n。And that's something you can derive。 We didn't have to guess。

 Oh let's think of an estimator of new。 You just write down the likelihood function。

 And it's a simple homework exercise to find the maximum of that function is at this location。

 So in contrast to standard statistics where when things get difficult and you need to make estimators。

 you end up scratching ahead a lot of。s， how should I make a good estimator here。

 the likelihood function。😊，Is a way of coming up with estimators。 If you want a point， a point value。

What about stigma， well。The maximum likelihood value of sigma is what you get when you press the sigma N button on your calculator。

So your calculator has two sigma buttons。 You shoved in the data into your little old calculator。

 It's got a sigma n button and a sigma n -1 button。 and the maximum likelihood。

Is what you get when you press sigma N。So that's him。Now。This con plot here isn't sort of symmetric。

 It it doesn't have concentric circles。 Theyre， they're sort of lopsided getting wider as you go up。

 And the reason for that is fairly intuitive。If it were actually the case that the mean is not equal to the data mean。

If it were the case that mu， the true underlying mean， isn't exactly the data mean。 For example。

 if the true value of mu is。Here， a little bit away from。The data mean。

Then think of what the variance probably is， given that all the data are sort of clustered around hereabouts。

The average distance， the mean square distance to one of those data points is a bit bigger because we've moved away from the data mean than it was when we were at the data mean。

 That means our estimate of how big the variance probably is is a bit bigger than what you would think the variance is if you knew that the true mean really is equal to the data mean。

So that's why the peak of this likelihood function here is offset a little bit upwards away from the value it has。

If we assume U is actually equal to the data mean。So that's why we've got this lopsidedness。

And if we take into account now the fact that we don't know mu and if someone told us， look， I I。

 I don't care at all what mu is。 I want to know how big the noise level is。

 because I'm interested in noise。Please tell me what I should believe about the noise。

 given this data。And given that we haven't got a clue what Mu is， except what the data is telling us。

If we now put that request into mathematics， what the requester is telling us。

 I haven't got a clue about what Mu is。 and I don't care。 They're saying。

 I've got a very broad prior on mu。 Okay， exactly how broad they didn't tell us。

 but let's just use an unspecified uniform distribution of some width thats sufficiently wide that we don't care anymore。

And then they saying， please tell me what I should believe about Sigma。

And the way you answer that question。Is。We can work out。Well， we can。

 we could imagine proceeding in two steps。 we could say。What would Muu be。

 He doesn't want to know Mu， But let's imagine inferring it anyway。Let's imagine we knew Sigma。

 and we've got the data。How would that inference work。Well。

 wed need to know probably of all the data given me in Sigma。

Multipliied by the prior probability of mu。Normalized by the probability of the data。Given me。Sorry。

 given signaligma。So I give myself a sort of inference， number one。Where。

 where we imagine inferring the thing that we don't care about。And。So you need your prior。

 which I said， is going be some broad distribution 1 over Delta mu 0。

So some very broad distribution like that。And then this probability here is the likelihood function。

But we're assuming that we know Sigma。What's this normalizing constant？ Well。

 this is the integral Bu。He back。G me in sigma。Times。Here here。It's an normalizing constant。

And often we ignore normalizing constants because they're just normalizing constants。

 So there's no dependence of the thing on the left hand side mu on the normalizing constant。

 But a rather beautiful pattern often occurs in these sort of inferences。

 that the normalizing constant that one person doesn't care about。

 namely person who only wants to know what mu is， is exactly the answer to the question someone else wants to know。

 namely inference number two， inference number two， what the first bloke asked us for was he said。



![](img/6bf61dddb98a7d46459efd00543906ad_31.png)

I just want to know what I should believe about Sigma， given the data。

And assuming that all this data comes from a Gaussian distribution。

And that by beare theorem is the probability of the data。

Given sigma times the probability probability of sigma。

Divided by a normalizing constant that he doesn't care about。

And the data dependent term that he does care about is the probability of all the data given sigma。

 And that is。There's normalizing in constant here。So there's a very common pattern that when you just follow the rules of probability to work out what you want to know。

 you'll quite often find that normalizing constants that to one person are unimportant normalizing constants are exactly the thing you need to know for the next level of inference。

 So here we need to do an integral with respect to mu of this likelihood function。

 assumingum a flat prior here。That's a simple homework exercise。 And when you do that inference。

You can work out。What the likelihood。P of data。Given sigma is as a function of sigma。

 So I'm gonna show you now a little graph。Of the likelihood。As a function of sigma。

 And what it looks like is。That sort of thing。It's actually got the shape of a gamma distribution。

 and it's got a peak。And the peak is at。Sig grade  line1。

So that's what your sigma red -1 button is for on the calculator in this probability view of inference。

 this probability based or Bayesian view。Okay。So what I've done here is I've reintroduced you to familiar things that you've known since you were 15 years old。

 You've had a calculator。 It had an an X bar button on it， It had a sigma n button。

 and it had a sigma n -1 button。 And now we know a meaning for these buttons。

 that they are ways of finding peaks of various likelihood functions and marginal likelihoods。

 This thing we drew here is called the likelihood function。😊，It's the likelihood of mu and sigma。

Thats this is the correct use of the word likelihood， by the way。

 The likelihood is when we're talking about the probability of some data conditioned on the thing that we call it the likelihood of。

 Alright， many people sadly use the word likelihood and probability interchangeably。 they say。

 there's a likelihood of this。 There's a probability of that。 and they're interchangeable。

 That's common speech。When we're doing statistics， I think it's a jolly good idea to be absolutely rigorous about the use of the terms and use likelihood only when it's the correct usage。

 which is in this context， The likelihood of mu and Sigma is the probability of the data given mu and sigma。

This thing here is the marginal likelihood。It's the marginal likelihood。Of。Sigma。

 which means it's the probability of all the data。Give in Sigma。And this thing way down here。

Is the marginal likelihood。Of the hypothesis。Which is the hypothesis that says that the data came from。

A single Gaussian with mean mu and7 deviation Sigma with prior distributions described by P of mu and P of Sigma。

There is another name that is sometimes given to this thing because it's such an important quantity。

 A marginal likelihood is a bit of a mouthful， and sounds。

Maybe too technical for such an important quantity。As we're gonna see in the next lecture。

 this is the important quantity。 If you want to do model comparison。 If you have。

 if you had an alternative theory for where this data came from。

 this is how well this quantity measures how well the theory H predicted the data that actually happened。

 So this is what we need in order to do model comparison。

 So we can either call it the marginal likelihood of the model。

 or we can also call it the evidence for。Model H。 that's not a universal notation， a universal name。

 but quite a lot of people use this name as an alternative name for marginal likelihood。Okay。

 so that was。A familiar beast， the gassian distribution。Answering the question。

 when you use Bayesian inference。What's what。Is the evidence in some way like。Okay， the question was。

 is the evidence a prior on the prior， I'll address that in the， in the next lecture。

 We're going to do a model comparison And what the evidence is。

 It's how well the theory predicted the data that happened。You。

 when you want to do inference of how probable this theory is compared with other theories。

 you need to put your own prior on those， those hypotheses。

 So the prior probability of the hypothesis is not the evidence。 That's， that's a different thing。

Alright， just as here， this is the likelihood， and this is the prior。

 So the role that the evidence plays in model comparison is the role that the that the likelihood is playing。

In this run of base theorem。So we'll do it again in the next lecture， and hopefully。

 it'll become clearer。In the next lecture， we're going to start off with the following exercise。

 This is an exercise that I took from an exam paper in the Cambridge physicsysic past exams from the year 1980 or so。

 And the exam question said。Imagine that a source is emitting particles， and they decay at locations。

 which we measure。 Those locations are exponentially distributed， and the length scale is Lada。

 And this little picture shows what that might look like if you're with X is the horizontal coordinate。

😊，And the white coordinate is just。It basting the points away from each other。

Decaser can only be observed， however， if the location falls in a window and the window goes from X min to X max。

1 to 20 centm。Now， N decays are observed， and there are locations， x 1 through x N。

 What do you think Lada is。That's the exam question。

 And I'd like you to think about that for the next lecture。And I'd like you。

 especially to cast your mind back before you ever heard of Bay's theorem as being the right way to do inference。

How would you have solved this problem before you knew about base theorem。

 And I'm hoping that you'll find it interesting to see how easy it is to solve this problem with base theorem and how this contrasts with。

 perhaps the difficulty of solving this problem with other ways you might have come across beforehand。

嗯。So that's what we'll do next time。Thank you very much for listening。 Yes， there's a question。

When I learned statistics， that end minus1。Yes， absolutely。 So the question is。In these statistics。

 literature and standard textbooks， people talk about number of degrees of freedom。

 And when you go from n to n -1， you've lost 1 degree of freedom。

 And that absolutely is a helpful way to think about these things。

 What we've done when we did this integral here， which we didn't actually do。 I said。

 do that integral as a homework question。 You've integrated out one parameter。

 And that gozzles up one degree of freedom of the noise。 If you actually knew mu。

 and someone gave you n data points， Then you would have n independent measurements of how big the variance is。

😊，But if we don't know Mu and we integrate it out， we've lost one of those。Degrees of freedom。

 if you like， of measurement of noise。 So the number。

 effective number of independent measurements we've got of the noise has been reduced to n -1 is definitely a helpful way to think about these things。

😊，It's also， you don't need to understand that concept to get the right answer。You。

 if you just write down the likelihood， do the integral， plot this graph and say。

 I'm interested in knowing which hypothesis did the best job of predicting the data。

 you will find sigma n -1。 and you don't even need to understand degrees of freedom。

 But definitely degrees of freedom is an interesting and useful concept。😊，Any other questions？Okay。

 thank you。

![](img/6bf61dddb98a7d46459efd00543906ad_33.png)

![](img/6bf61dddb98a7d46459efd00543906ad_34.png)