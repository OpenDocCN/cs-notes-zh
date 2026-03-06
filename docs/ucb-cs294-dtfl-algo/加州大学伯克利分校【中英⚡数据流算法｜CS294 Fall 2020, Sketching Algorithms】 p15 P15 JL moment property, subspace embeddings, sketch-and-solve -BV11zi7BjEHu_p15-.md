# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p15 P15 JL moment property, subspace embeddings, sketch-and-solve -BV11zi7BjEHu_p15-

![](img/f6c71688f78e00ebac2311666589c956_0.png)

Okay so hello everyone， we're going to keep talking about randomizing linear algebra sketching algorithms。

Last time we started with approximate matrix multiplication where you measure error in the Frbeous norm。

And we said。There is a sampling based approach。Where if you're trying to multiply a transpose B。

 what you do is you stamp， you know， you repeatedly， let's say m times。Sample a row。Right。

 so we said before a transpose be。Is equal to the sum of AI， B transpose。喂。Or add from one to N。

So you can express that product as a sum of n outer products。

So if you sample one at random and appropriately scale。

 that'll be an unbiased estimator and the question was， how many do you need to sample？

And also what's the best distribution to sample from and it turns out that the right distribution is not the uniform one。

 but rather to sample I with probability proportional to the product of the norms of AI and BI。

I apologize the video for last lecture got up a little late it is up on the website now and the notes will be there soon。

 I did not do the analysis of the variance in class that's going to be in the notes。

 but I did do the you know show you that it was at least an unbiased estimator。

So that was the original approach。The Dea projects Junaus Cannon and Mahoni。

For a approximate matrix multiplication， that would via sampling。Well， the one downside of that is。

 you know， it is。It is。Depenent on the actual matrices A and B。

 because you need to know what the roor of A and B are。

So if you're in a setting where for example A and B are being updated in some say streaming fashion。

 well how can you choose the sampling probabilities at the beginning you don't know them because you don't know A and B So another thing you can do which gives you similar results we're going to see now is to use a JL kind of approach。

Where you approximate a by pi A think of pi as a kind of jail matrix， you approximate B by pi B。

And then you approximate a transpose B by pi a transpose pi B。Okay。

 and you can show that as long as your jail distribution is good and you have an enough rows。

 your forennous norm of the difference will be small with high probability。

 I'm going to show you that now。And I should mention， by the way。

 that even the sampling approach is also approxiating a transpose B by pi a transpose pi B。

It's just that pi is not a jail matrix， it's a sampling matrix right where what does a sampling matrix mean。

 it means that each row of pi has a one in a random location corresponding to the I that you sampled and zeros everywhere else。

You know， normalized by square root of PI like we did last time。But again， that pie is。

This is going to be drawn from a distribution that depends on A and B because the sampling probabilities depend on A and B。

Okay。So good now let's let's try to understand you know。

Why should the jail kind of approach work for approximate matrix publication。

 and I hinted at it last time。All right， so the point is。What is a， A is this matrix。A one。

Transpose all the way down to AN transpose。And then b。Is this。This matrix。He want transpose。

The entrance transpose。嗯。And pi a transpose。Actually， I guess I should。

So now I think what I want to do is actually change rows and columns so pii transpo pibi。

So what is that， you know， if you look at the IJth entry of that。It's saying。

So look at the Ithe column of pi A and the I column of pi B and take their dot product。

I got a little slightly dyslexic hereator。For for the purposes of this。

 I think what I want to do is I want to actually。Right the other way around。

So let's say this is a one。This is V1。So right， so if you apply pi。

 that means you're applying pi to the matrix column by column， so pi a。Looks like。

The first column here would be pi A1。The next column would be pi a2。Et cetera。

So you're taking the dot product with the I column of pi A with the J column of pi B。

 so this is just pi AI do with pi Bj。And I apologize again， I guess I turned。

SSuper subscript super super subscription subscriptionscript， so thiss be consistent。

So and then if you take minus a transpose B， that's going to be minus Ai。 Bj。Right。

 so if you look at。This implies that from be norm squared。Pi a transpose pi V。

Minus a trans supposed to be。It certain squared， this is just the sum overall IJ。Of。

Pi AI do pi Vj minus AI。 vj squared。So already you can imagine doing a kind of union bound argument and in fact。

 if you look at you know the jail approach。I mentioned was first introduced by Char 06。

For approximate major transportation。And if you look at his paper， I mean。

 this is basically what he did， he said， look。If I preserve distances， I preserve dot products。

So all these all these doc products are close to what they should be if I union bound over all IJ。

Then I can say that all of them， all these dot products are closed for all IJ simultaneously。

And then therefore， the sum will be， you know， close to what I want。

 So that was his original argument。You do lose something， though。

 because you have to union bound over all INJ。Which means that， you know， with JL， your failure。

 you know， your dependent on the failure problem is log whenever deelta。

So if you're union bounding over all these things， you need to set delta to be polynomly small to union bound。

 which means you're going to pick up an extra log factor in your bound from that right log dimension factor。

I'm going to show you an argument now that I think it's worth internalizing。

What's really happening in this argument becauses it's the useful I think way of thinking in general for other kinds of probabilistic analyses。

 it turns out that that union bound is 100% wasteful and you can get you know you can get a bound as if you're only trying to preserve a single vector even though you're preserving the sum。

You don't have to unbound on East Sman individually。Okay， so how do you do that？So， definition。

A distribution D。Satisfies。The let's call it the Epsilon Delta P。JL moment property。Okay。If。

For all Z of unit norm。We have that the expectation over pi。Of。Let's look， I guess， pi Z。

L2 norm squared -1 to the P of power。Is at most epsilon times delta into the1 over P？对。

And here I'm assuming here that let's say P is something that's at least one。Okay。

So what is this good for， I mean， why am I introducing this？The utility of this is。

Right like if you're trying to prove that let's say a probability of a pie coming from this distribution。

 and by the way， this pi is also going from this distribution。

If you want this to be true that you have the jail limit that you have a distributional jail。

 distributional jail says that。This thing is small。Pi Z L2 norm squared -1。

 The probabilityvalentness is bigger than epsilon。Its small， right。That's what DJL says。

But if you raise both sides to the P of power and do Markovs inequality。

You know that this is always true。 This is at most the expectation over pi coming from D。

Of pii Z L2 norm square root minus1 to the P of power。Oh， and I guess I should have said。

Rather this should be epsilon to the P times Dlta of those whats so。Over up side to the key。Right。

So if your distribution D satisfies the jail moment property。

 it means that the numerator is at most epsilon to the p times delta。

 which means that this thing is less than delta， less equal goes to delta。If the。Satisfies。

The epsilon Delta PGL element property。 so I mean， satisfying the jail Mo property is， you know。

 is's just a fancy way of saying that。The distribution gives you DJL viaM Markovs inality on a high enough moment。

Okay， that's all it's really saying。And it turns out that kind of all the distributions that we've been talking about so far that give you jail do have the moment property for some choice of epsilon delta and P so for example。

Take the camp sketch matrix where a pie looks like this。Each column has exactly one non zero。

 which is a plus minus1 and the rest of the column is zero。I let's say this is M is the number of。

M is the number of rows。Right this has the Epsilon Delta PGL moment property where basically so count sketch。

Where M is at least some constant times1 over epsilon squared delta and p is2。In other words。

If you at that， if you look at the variance of pi Z L2 norm squared， now， you know。

 if you bound the second moment。Then。You can basically prove that the probability of deviation is at most epsilon with probably at least one minus delta。

As long as M is at least what epsilon squared delta， that's just via this is via the variance bound。

Okay。So essentially you prove that the variance is roughly one over or O of1 over。Okay。

So we did this before when we were talking about kind of。

Speeding up the AMSS sketch via Sprsa matrixtrix。Of course whenever delta is not great。

 you know we usually like m to be log whatever delta so you can get like you know。

 let's say I plus minus1 entries。嗯。How do we analyze that。

 we analyzed it using the Han and right inequality， right， which really is abound on all the moments。

And if you unwind that proof， inspect it， look at what moment did we use exactly to get the delta failure probability。

 we use the log order or Delta moment。So here you can set M to be something like log， whatever delta。

 over up on squared。And P to be something like some constant lot we deta。You know。

 sparse jail is another one。You know， basically similar thing with S being longer adults over epsilon。

You can also even do it with fast jail。If you do it fast J。

 I think you're going to end up needing P to be a little bit bigger if you unwind kind of。

 what moment do I really need to make the whole thing work？

I think end up getting away with something like P is like roughly log of whatever epsilon delta。And。

M is something more， you， that's a different。 So M is going something like。

So it maybe like log one over epsilon Dlta log one over Dlta over epsilon squared。

 maybe a little bit better than that I'll put the precisely in the notes， but where the point is。

Yeah， the where do the values of P come from， like are they related to M？Yeah。

 I mean so the point is， I guess， right if you look at， you know， if you look at， let's say。

 I don't know analyzing the second the second one here， IED plus minus one entries。

 we use Hansen right， right？So if you remember like let's say this one right here。Great。

We use Hanson right， let's call this this is the error random variable， let me call it something。

 let me call it Z。Right。It's a quadratic form right， I mean， it looks Z transpose。So remember now。

We had this thing before we said like z transpose， pi transpose pi z。Right， can be expressed。

 It's just the same thing as sigma transpose a sigma。Where A was this block diagonular matrix。

So if you look back in the notes， you can see this all over again。

 but A looks something like Z transpose， easy transpose， easy transpose。And there's a one of here。

And Hanen Wright said that。If you look at this error random variable。And look at its por。

It's at most， know up to a constant root p times the phoennous norm。Plus p times the operator arm。

Right， and then， you know， the way you might， you know。

 the other way we've been talking about handsome right is like。For all lambda greater than zero。

 the probability that z is bigger than lambda。Is that most？

U to a constant like e to the minus C lambda squared over fromenia squared。

Plus e to the minus C Lada over operator norm。But these two things right here。

A equivalent to each other。So to say that for all P bigger than equal to one， you have norm bounds。

 moment bounds。And to say that， you know， you have taildowns for all lambda bigger than zero like those two are equivalent to each other and that's if you want to see again a proof of that。

 that's that's in the notes in the probability review section。

But the point is we've been analyzing multiple of these like sparse gel and the middle one plus minus1 trees。

 we analyzed both of them using Hanson right。Hanson Ri is equivalent to bounds on the moments。

So if you just inspect the proof and look at like which moment did we use， which P did we use to get。

The results。It turns out that we used PD being something like logwin Delta。

And M we set M to be loggged whatever del over reppsilson squared。

So you can go back and look at the proofs and realize that this is what we were doing。And indeed。

 it's what we're doing so all these things we've been analyzing so far。

Have been all based on moments， even Kramer Ward right。

 Kramer Ward ultimately was also using Hanson right。

And so answer right again is just based on moments。 So yeah。

 so all these things that we've been talking about do have the Epsilon Delta PGL moment property for some P。

Okay， anyway， any other questions？So now that we now that we've introduced this concept first。

 let me talk about。How to use it for kind of dot products。So， claim。Suppose。

D has the Epsilon Delta PGM moment property。Then。For all X Y of unit norm。If you look at。

The dot product。So here， let's look at this。P诶。X dotted with pi y。Minus x dotted with y。

 look at the penum of that that's going to be at most。Epsilon times delta into the one of repeat。

Remember， the P norm is the PF moment raised to the one over PF power。So you know。

 if you just raise both sides of the P of power， what I'm saying is that。

The Pth moment of this difference in dot products is also bounded by epsilom of the P times delta。

So the definition of jail moment property just says that you preserve norms， right。

 your moment bounds on the difference of the norms is small。

And just having that alone implies the same bound on dot products。Okay， and why is that true？

So proof of this， it's something similar to something you've already seen。

 which is just the observation that look。X plus y L2 norm squared is equal to x squared plus y squared。

Plus， twice the dot product。And also x minus y squared。Is equal to x squared。Plus y squared。

Minus twice the dot product。Okay。Which implies。If you just move things around。

 you'll get that x dotted y is equal to one fourth。X plus y squared minus x minus y squared。Okay。

 this follows just by rearranging， nothing fancy。Okay。

 so now let's do this both to x dot y and pi x minus and pi X dot pi y。 this implies that。

Pi x dot pi y。Minus x dot y。P norm is equal to。Let's rewrite x dot y and rewrite pi X dot pi y。

Equal to one fourth。Times。嗯。I see what I want to say is。Pi X。Plus pi y L2 norm squared minus。

X plus y Hesson norm squared minus。Pi x minus pi y Line norm squared minus x minus y Ls norm squared。

Peter。So I just rewrote。X dot Y using the identity above。

 and I rewrote pi X dot pi Y using the identity above and did a little bit of rearranging。

And then now I can do triangle inequality。This is at most。嗯。One quarter times。Pi x plus y。

Elson arm squared minus。X plus y L to norm squared。Penor。Plus。

Pi x minus y L2 arm squared minus x minus y。Elterham Square， Por。And then I can multiply by you。

 multiply and divide by the same thing， so basically multiply by one。But I mean by that is。

 let's just divide by xse。Let's just divide。By the norm of x minus y here。

And let's divide by the norm of x minus y。And that's okay as long as we multiply it back on the outside。

 so let's multiply it back， we're going to multiply it back by x minus y squared because because there's a squared here right so if we divide by it。

 we have to multiply by the square。And let's do the same thing here。嗯。Divide by x plus y norm。

 divide by x plus y norm。And then here on the outside。Multiply by the square。Does that make sense？So。

Okay， good and then now。What do I know this is know this is pi times z L2 norm squared minus z L2 norm squared where z is。

 for example， x plus y。Over the norm of x y。 So Z is a unit norm vector， right。

 this is this is what I'm calling Z like this vector。Let's say I call it Z。It's a unit norm vector。

So I can apply the fact now that D has the Epsilon Delta P jail moment property。

And I can say therefore this moment is bounded。So this is at most。One fourth times。Here I get。Yeah。

 I'll pull it out to the outside。You know， epsilon times delta to the1 over P。

 and then I have that one fourth。And then here I have x plus y squared。Because I have this part。

So I have to keep that x plus y squared。Okay， and similarly， I have the same thing over here。

 but I have plus x minus y squared。Okay， and then again， so now there are no more p norms。

 right I got rid of I did I already applied my por。

And then now I can again use the parallelogram rule。

 This is the same thing as this is a this should be a canvas a plus， so this should be x squared。

Plus y squared。Plus， twice the dot product。This is x squared。

Plus y squared minus twice the dot product。So these dot product canceled。

What's the norm of x squared？Right。Right。X has norm 1， Y has norm1。

So this all this is also known as four， right， one plus one plus one plus one is four。

So this is equal to。And the forest cancel epsilon times delta to the 1 over P。Right。

So just knowing that I have a certain kind of moment bound on like preserving。

Distances are preserving norms of vectors。Autoomatically implies that I have the same quality of moment bound。

 I don't even lose a constant factor， I have the same quality of moment bound when I'm trying to preserve dot products。

ok。So now let's go back to understanding approximate matrix multiplication using jail。对。So， back to。

Approximate matrix multiplication。With jail。The claim is。嗯。If。The distribution D satisfies。

The let's say， Epsilon Delta P JL moment property。For some P， which is at least two。Then。

The probability that I deviate in forennious norm from the true matrix product。

By more than epsilon times the Frgen number a times the Frgen number B。Is that most Delta？

So all these things that we showed satisfied jail in the past。Like the count sketch matrix。

 you know for peoples too with a bad M or a sparse jail or fast jail or whatever。

 since they all satisfy J MP P you know for what for some P。

I basically automatically get that they give you approximate matrix multiplication as well。

YouWithout having to。Set Delta to be smaller， you know。

 you don't have to set Delta be smaller to Union bound or anything like that。

 it just automatically works。对。So good。 So let's try to understand this。 So let's define M。

To be pi a transpose pi B minus a transpose B。 And we already said that then you have something like MI I J is equal to。

Pi AI dotted with pi BJ， where AI is the I column of A BJ is the J。A you callB。Minus a transpose Ai。

bj sorry。So that implies that m for being norm squared。嗯。Is。

Is equal to the sum overall Ij of this thing squared。And again。

 what I'm going to do is I'm going to write this， let me define now。

AI Tilde just defined it to be AI divided by its norm。Okay。

So I can write that this is the same thing as pi A tilde do pi Bj minus Ai tilde do bj tilde。

And then let me multiply it by the norm of。multiultiply back by what I divided by。

 so multiply back by the norm of AI times the norm BJ。So the Frbini norm squared then。

There is some overall IJ of。This thing's weird。Pi AI tilda。H BJ tilda。Might as A I killed a。

DidJ tillda。Squared times AI Loon norm squared times Bj L norm squared。

And kind of why am I doing all of this， like why so right the point is。

When where am I going where I'm going is the second moment method right where I'm going is look I'm trying to bound the probability that the Frmino storm is large I say look the probability that the。

The problem at the Ferminian store is large。Is the same if I square both sides。

 so it's the same as if I square both sides。And then I can apply Markov that's less than the expectation。

Actually， let me raise both sides， in fact， to the Pth power， I should say。

That's less than the expectation of。And for me， it's remember the P。Divided by lambmb the P。So my。

 you know， the name of the game right now is try to get， try to get a bound。On this thing。

Using the jail moment property。And if I can do that， then I'm golden， right。

 then I can just plug it into this Markov and I'm done。Okay。

So now we understood at least what the Frennus normorm squared looks like。Okay， so now。

I'm trying to understand now the P norm， right because this is basically this is the P norm race of the P。

 the Pth moment is the P norm of the P， so I want to understand the P norm。

So let's look at the Frennous norm of M。Por。That's the same thing as the expectation of the Frbeus norm。

Raace the P。To the one over pe。But you know， Frbeius norm has a square root in it and that makes things more complicated for me。

 I prefer dealing with the square of the Frbeus norm because then it's some it's there's a summation there and it's more linear。

So what I'm going to do is I'm just going to square this。And then raised to the pure were of power。

I haven't changed anything， right that's still the for norm to the P just that。嗯。

I just wrote it in a different way。And I'm going to use the fact that， you know， you'll see Sue。

 and I'm going to use the fact that the P over two norm is still a norm。And that's why I required。

 actually。That P is at least two。That way P over two is at least one， so I have a norm。

And then this one over P on the outside。Is the same thing as light2 over P。

And then if I take the square root of the whole thing。So this is also known as。M F squared。

Pier over2 norm， all raised to the one half。Okay， does that make sense。Okay。So now good， let's try。

 and now。Understand this， let's try and bound here over two normal MF squared。

So now we're just going to write out what MF squared is， that's what we wrote above。So。

 this is equal to。诶。And also just to make things。Like not have to you know not be bogged down with too much notation。

 let me just call this random variable like this this is a random variable because it depends on pi。

This one right here。Let me just call this like X IJ。Okay so that's the that's a random variable。

' without it's defined without the square。ok。So now I know that the Perennian storm squared。

 I can write that thing as。The sum of all I J。Of。AI L pseudo norm squared。BJ， L2 norm squared。

 X I J squared。Pier over two to the one half。Okay。And now I can do triangle inequality。

And then this is at most now， the sum over IJ。Of。嗯。Well remember there's a square root up above。

 so when I pull out a constant factor on the inside， I have to make sure to take the square root。

 so I'll pull out AI to AI L2 norm squared。But I have to square root it。

 So I don't have the square root anymore。 So I have the norm of AI。Times the number BJ。Times。嗯。

X I J squared。Pier over two to the what half。Okay。But again， now I can just， you know。

 what is the definition of what does this mean？This means this thing here means。Expectation。Of X。

 I J to the P。嗯。No， it's actually absolute value to the P。To the two or repeat of the one half。

So to the one over repeat。喂。So this XIj squared P over 2 norm all to the1 half is again。

 a really fancy way of saying the P norm。So this is just equal to。Some of all IJ。Of AI。Bj。

Times the por of Xij。Again， what is XIj？It's this difference of these two dot products， right。

 where AI Tilda has a unit norm vector， BJ Tilda as a unit norm vector。

So we can apply the lemma on the previous whiteboard。To say that by the jail moment property。

 this thing here is at most。Epsilon times Delta。To the1 over repeat。

So overall this whole thing is at most。Epsilon deelta to the 100 P times the sum over all Ij。

OfAI times BJ。And then now I just finish it with Kohi Schwartz。喂。Kshi Schwartz says， I mean。

x dot y is at most the norm of x times the norm of y。So this is at most。

Epsilon delta to the 1 over P times。The sum of。AI squared square root。Times the sum of。

BJ squared and square root。What's another name for this？Like， what is this？

Make sure you're on the same page here。The Frbeius norm of B， Yeah， exactly， the Frnous norm of B。

I'm just summing up the entries like squared column by column basically， right？And similarly。

 this is the Forens Nor Bay。嗯。So then now。You plug that all in here。Right here。

Just set Lambda to be exactly this。Lambda is epsilon times the perbenious norm of A times the perbenous norm of P。

So you raise it to the P of power。You've got epsilon to the P AF to the P， B F to the P。

 and is denominator。And then the numerator。The numerator is exactly all of this raised to the P。

You take that thing and you raise it to the P， that's what goes in the numerator。

For being known to the Pe cancels。BF to the P cancels， epsilon to the P cancels。

And the only thing you're left with is delta to the1 over P raised to the P， which is delta。

Right so your failure probability is at most Delta， which is exactly what you wanted to show。对。

So good， so that's all I want to say about that is that you get， you know。

 having this gem property gives you A&M the defense of the convenience storm for free。

Questions about that。H。So when we said that that like norm P of X I J is less than equal to epsilon datata to the one of a P that was using the。

嗯。Like the jail。You're saying the last inequality down there as you know。

 the one right before Kohi Schwartz， yeah， I was using this， right？

I was using this yeah right because XIj is exactly of this form XIj is some difference of dot products。

With unit owned vectors，And before that， when you like split up the the norm using in tri inequality。

 we also like a。Relying on the square root， satisfying the triangle inequality。 Like。

 I guess that's true。 I just hadn't thought about it before。Yeah。

 so if you don't want to think about it， yeah， so we are using the fact to write that like。嗯。

The square root of a plus B。Is at most the square root of a plus the square root of B。

If you just square both sides。The left hand side is a+ B， the right hand side is a+ b plus more。Yes。

 I was using this fact。Good， good good observation， any other questions？Okay。So okay， so good。

 so that's for being nor approximate matrix multi。嗯。Let's now try to move to another norm。

What about approximate small location with the operator dorm？So what I want is that， you know。

 ideally， I want。嗯。A transpose B minus say some pi a transpose pi B。Operator norm。

To be less than say something similar，8ps sometimes times operating away eight times operating。so。

It's going to segment into， I guess， something that's more interesting， which is if I do this。

 we're going to focus on。We'll focus on like B equals a。Okay。For the rest of the lecture。

 I mean you can you can do stuff for B not equal to a。

 but in the applications that we're going to see of this， it's most interesting when B is a。

 so I'm going to focus on that。So what does this mean， this means that。

A transpose a minus pi a transpose pi a。Operator norm is at most epsilon times a squared。

Like what is the operator norm？The operator norm is， you know， this is。

 these are both symmetric matrices， right， like， I mean， I mean， the left hand side。

A the left hand side of this is a symmetric matrix。 This thing is。Kind of the soup。

Overall Z of unit norm。Of Z transpose times that matrix z。

which is the same thing as like the suit overall z unit norm。Of。嗯。p a z。

El norm squared minus Z Ls norm squared。And in the right hand side。

this thing is also the same thing as the operator number of a transposese。

So the right hand side is like， so this is saying this is at most like the soup overall W。Of。

A Wl2 norm squared。Right， so to say to say that。Pi is letting you do AMM with respect to operator norm。

It's basically the same thing as saying that this is true。

It's the same thing as saying that this inequality is true。

But we're going to get something that's even stronger in today's lecture。

 which is the notion of what's called the subspace embedding。You know， we will study。Hi such that。

For all Z of unit norm。We have that。H a。There's an epsilon here， right， there's an epsilon。诶拍 a z。

Ill say I'm squared。Minus z L2 norm squared， just which is just one， right？I mean。

 this is also just one。Minus1 is less than equal equal to epsilon。Times。The same Z。

 So instead of the super over w， it's the same Z。 so that's azel to squared。Oh， sorry。

 I just realized be this should have been easy norm this should have been easy， yeah。

 so forget that it's not one。Azy LC squared。And then similarly， this should be easy。

So what this is saying is。For any vector Z pi a Z is roughly the same norm as Z。Okay， and this。

 by the way， is， this is called， you know， this concept。It's called like an epsilon。 if this is true。

 we'll say that。Pi is an。Epsilon， subspace embedding。For the column space of a。Okay。

 so what's the definition， let me give you the definition of a subspace embedding。So， definition。嗯。

Pie is in。Epsilon。Subence， why is my。We pies and epsilon subspace embedding。For let's say。

 some linear subspace。E， which is't say a subsetstive RD。If。For all Z and E。

I' would say for all X and E。DoesDoes matter。嗯。If you' looking at pi Z L， let me call it x actually。

Pi Xl2 norm squared has roughly the same norm as like one plus epsil pi XL norm squared is roughly the same norm as X L2 norm squared。

If P satisfies this， I will call pi an Epsilon So embedding for E。Okay。And。😊。

Now notice that I want to write an equivalent equivalent way of saying this， so what is a subspace？

Well， any subspace has an orthomal basis。 so like equivalently。You know， let you。Which is， let's say。

It's a it's a D by。Dim E matrix。Have orthoormal columns。Forming a basis。For E。Then first of all。

 I mean， without even the orthoor， just the fact that it's a basis that means that E can be written as the set of all vectors z or x。

Such that。嗯。There exists to see。You know， where。X is equal to U Z。In other words， you know。

 this is the same as instead set of all vectors use Z where。Z is an R。你什么 me。Let me make。

 I'm just going to change notation on you a little bit sorry but this is going to make things simple later。

I'm just going to say that D is the dimension of E and E E lives in an RN。

 so E is a D dimensional subspace of RN， so that means U is an n by D matrix。

So E is just the set of all vectors of the form u times Z。

So now what does it mean to be a subspace embedding？Epsilon somespace embedding。What it mean。

 it means we said it means that for all Z and R D。嗯。Hi you Z。

L2 norm squared is less to go to 1 plus epsilon times the norm of Uz L2 norm squared is at least one minus epsilon times the norm of Uz squared。

What is U Z L two norm squared， that's the same thing as。Z transpose U transpose U Z， right。

 this is the norm of U Z L norm squared。But you has orthonal columns。

Which is the same thing as saying U transpose U as the identity matrix， right。

 What's the I Jth entry of U transpose U。 It's the I column of U dotted with the Jth column of U。

 So if I equals J， it's one， if I is not equal to J at's 0 because the columns are ortho the normal。

So this is the same thing as z transpose Z because u transpose U's identity。

 which is the same thing as z L squared。So this is the same thing as saying that。嗯。One minus epsilon。

Z L2 norm squared is less than equal to。Pi U Z L squared。

This also equal to1 plus epsilon z square squared。Or if I subtract？

If I subtract Z norm squared from both sides， this is saying that。嗯。P u。

Ll2or norm squared minus z L2 norm squared。Is at most epsilon times z L squared。

 this is like for all Z。And this is the same thing as saying that the operator norm。Of piu。

Transpose par U minus the identity matrix。Is at most epsilon？唔杰。So that's what I want to emphasize。

 namely this definition。Of what it means to be a subspace embedding。Is equivalent。

To this this other notion。If I had to find some space embedding by the bottom box。

 it would have been equivalent to the top box。Okay。Which， by the way， I mean， looks a lot like。嗯。

I mean， it looks a lot like JL， like think of a DJL what does DJL say DJL says that for all unit vectors。

 I mean， let me just write this down and you can see the similarity。

Say DJL says that kind of for all for all unit vectors U。What it mean to be a unit vector。

 so for all UN and RD？Such that u transpose u is1， meaning it has unit norm， the probability over pi。

That pi UL2 norm squared， which is the same thing as。Pi U transpose pi U。Minus one one is of course。

 just the one by one identity matrix。The problem， this is very than epsilon。Is that most Delta？

Right that that's like what that's what it means that the distribution D here。

gives you distributional jail。And you can imagine then defining something similar for subspace embeddings where you say for all oh and actually maybe I should have。

Let me call this N。So I get to find something similar where I say， look， U is not a vector anymore。

 use a matrix， so a vector is just an n by one matrix， this is let's make it an n by D matrix。

And instead of u transpose u equals  one， I'll say u transpose u equals the identity and the D by D identity。

And let me here also put D by D identity， and let me put operator norm。So kind of syntactically。

 this looks just like。A natural generalization of distributional JL。嗯。

And this is what I'll call an oblivious subspace embedding。so。A distribution D。

Over pie satisfying the above。Is called。And let's say。Epsilon Z。Olivious。Some space embedding。

What it means is。Kind of for all linear subspaces E。Of dimension D。With good probability。

 a random matrix drawn from this distribution。Will be a subspace embedding for that subspace for E。对。

And it's a natural- if you write it this way， it's a natural generalization of distributional jail。

Okay。😊，Now， just recall。嗯。The definition of some space embedding。For a particular subspace。

 there's no randomness in the definition。 Like， I am allowed， I am allowed to pick。You know。

 just you know， a deterministic matrix that is a subspace embedding， right？嗯。

Or I can do something that's kind of oblivious like this where I'm picking a random matrix that doesn't even look at the subspace。

老师啊。We'll see different ways of constructing some based embeddings now， some ob， some not。

 some not even random。So。Before I talk about how to get Subspace embeddings and what they're good for。

Are there any questions about what the definition of a subspace embedding or the definition of an oblivious subspace embedding？

Is that all here？I these Gs you added on with like a modification。Well， D， yeah， so D is the。

So you can think again， here when I've modified it with the red ink， U is now a matrix。

 an N by D matrix with orthoormal columns。😡，So you can view the columns as the basis an ortho basis for some subspace。

Namely for the column the space of view。Okay。So。This is just saying that with high probability。

 a random pie， know， for any fixed subspace of dimension D。

A random pie will preserve it with high probability。It'll preserve all vectors in that subspace。

 high probabilitybil。No it's oblivious because it works for subspace It's oblivious because you pick pie without even knowing what the subspace is。

Sort of like JL， you pick your JL embedding without even knowing what the vectors are that you're trying to preserve。

So。😊，So good。 So， you know， how do we， So first， let me talk about like， how do you get。

How do you get some based embeddings？Okay。So what is。So usually for us。The subspace is given as。

Not that it matters， but。Usually for us， we're going to see like in the applications。

 the subspace is often going to be， you know， the column space on a given matrix。

So I'm just going to give you a matrix A， which is some big matrix。And let's say it's a very tall。

 you know， usually for us， a is going to be like this。A very tall matrix that's not too wide。

 so think of it as like n by D。And I'm going to want to preserve its column space。

 its column space has dimension at most D because there're only D columns。Okay， so。

Kind of the subspace is implicit in the sense that。

I don't actually give you as input on an ortho basis for the subspace。Given A。

 you could try to compute an ortho thermal basis by， for example。

 doing Gham Schchmidt or computing the SVD of A， that would give you an ortho thermal basis。

But you know are that's expensive in terms of computation， that's an expensive operation。

So if you know， so let's say first of all。If you know the subspace， if you know an orthooidnal basis。

For E， let's say that it's like a matrix U， which is an N by D matrix。Utranspose U identity。

E is equal to the calm space of you。So if I know such an a thermal basis。

 I claim that a great thing you could do is choose pi to just simply be U transpose。喂 why。Because。嗯。

If x is an E， that implies that x is equal to U Z。For some Z。Which implies that pi X。

Is equal to u transpose U Z， which is just z。And， you know， we already know that。

X L2 norm squared is equal to U Z L2 norm squared。Which is equal to Z2 norm squared。

Because you transpose you as identity。So this is like perfect equality。

This pie does not introduce any error at all， it perfectly preserves the norm of the entire subspace。

And this thing maps。Maps and dimensions down to D dimensions， right？So Gelani。

 the pie is just a change of basis to me。To the the basis of eat， right， in that case。Yes， well。

 Lords。I don't know yeah， guess I。Right， yeah， so you're telling me what the coefficients are。

 if you try and express， if you try and express X in the basis U。

 you're telling me what the coefficients are that's gonna to be the entries of。

OfOf pi X is that right that's what you're saying， right。

 you saying it's the change of basis from the standard basis to the basis that it would be in in for E。

 I think or the other way around one of those。 Yeah， I mean， I guess I guess yeah I guess I。

It depends on what change of base means because we are also changing the dimension， right？Oh right。

 originally we're in dimension N， now we're in dimension D。

 but you can also you can also imagine that we complete the basis into a full n dimensional basis。

 but that doesn't matter because all the other things that we complete all the other vectors we add in。

A going are going to be orthogonal to x anyway so all those dot products are going to be zero so yeah that would be then be a change of basis in the same dimension。

Okay。Yeah， good so this is like perfect right because this gives epsilon equal to zero。

which is the smallest epsilon you can want， and it gets you down to dimension D。

 and I claim that you can't hope to get that down to dimension less than D。Just for reasons of。

 I I guess kernels right so if you if you have a D dimensional subspace。

And you hit it with a matrix that has fewer than D rows。

Then something in that subspace is going to be in the kernel。

 like some non zero vector in the subspace is going to be in the kernel。

 which means you're mapping it to zero。Which means you're definitely not preserving its norm， right。

 its original norm， let's say was one。Now you're mappingping into the zero vector。

 you have not preserved it。D is like the smallest dimension you could ever hope to get。

 and you're getting it with absolutely no error。The downside of this is that you need to know an orthophnal basis for E。

 and again， if E is given to you as， let's say the column space of a matrix A。

And a is a might not have orthoormal columns， then it's expensive。

To extract orthonormal columns from a right you either have to do some Grm Schchmidt or SVD or whatever。

 which is going to be expensive。Computationally expensive。So anyway。

 this is like the holy Grail best kind of。B you can hope to get。What else can you do。

 you can do sampling。That's another thing you get up to do。 Again。

 a transpose a is equal to the sum over all I from one to n。Of AI， AI transpose。Okay。

I got it out here， so now here， I guess I'm going back to my old ways where。

The AIs are actually the rows， not the columns， sorry about the mass confusion。

So you could ask yourself， well， what if I sample and I say， look， this is roughly the same thing。

 hopefully。As some sampled version， so some I goes from one to N。Of。Let's call it A to I over Pi， AI。

 AI transpose。Where。Eta I is equal to one。If we keep。row eye。And0 otherwise。And you know。

 like the probability that A to I is one is P。And that's why we divide by PI so that。

The expectation of this thing is correct。So that this is。



![](img/f6c71688f78e00ebac2311666589c956_2.png)

July a year。Frozen or muted。

![](img/f6c71688f78e00ebac2311666589c956_4.png)

it seems I was booted out， you still can you hear me？Yeah。Can you say that more time。Yes。

 we can hear you。 now it seems that my audio， I don't know why this keeps happeninging my audios。

 Yeah， okay say say hello over more time。 Ho， Okay， great。 So now it's working。😊。

And now let me get back inside of my whiteboard。Okay， so this is where we were。嗯。Okay。Right so。

What I'm doing is。I I'm going to end up with a variable number of some ends because for each row independently。

 I'm going to decide whether to keep the row or not keep the row。 So with probability P。

 I keep the I row with probability 1 minus pi I ditch the I row。

A to I is this indicator random variable that keeps track of whether or not I kept the row。

I divide by PI so that this thing is an unbiased estimator of a transpose I want the expectation of this to still be correct to be a transpose Okay。

 so that's one thing and again there's a question of now what should I set the sampling probabilities to be。

With Frbenius norm， approximate matrix multiplication。

 we said that PI should be proportional to the norm of AI times the norm of BJ or sorry。

 the norm of AI times the norm of BI。Um is that the right sampling probability forspace for getting a subspace embedding？

And it turns out the answer is no， it turns out that the right sampling probability is something called leverage scores it's related to the leverage scores of a。

 we're going to get to that soon。And then so that's that's so like so all of this， by the way。

 I should say I should title this is。U。How to get。Somespace embeddings。Okay。So option one。

 you know an orthoal basis that it's easy， option two。

 you sample rows of a according to some distribution that you need to figure out。

Option three is to do in ob Bolivviia subspace embedding。嗯。And so let me say a little bit more about。

 you know， so the question is like， what should the distribution be right for W subs？

So I think the first bullet here is like set pie to eu transpose。

 there's not really much more I want to say about that。

But I do want to say more about sampling and aia subspace embeddings。

 namely what should the distribution D be for OSEs and sampling what should the probabilities be。嗯。

So' let's talk about them in reverse order， and I think I'll be able to say what I want to say about them。

And then we can move on to more applications。慢慢地。Okay。

 but actually even before even before I talk about these two。

 I want to say what OSEs are useful for because I've said a whole lot about OSEs so far and somespace embeddings without telling you anything about like why you should care about them。

就。Let me give you an example。Application。Of subspace embeddings。Okay， and this is， this is， you know。

Call。This had a discussion and solved paradigm。Due to Chars。In0，6。

And the idea is take a problem like least squares regression。

So beta least squares is equal to the minimizer。Overall， beta of the norm of x beta minus y。

El through norm。ok。😊，So you suddenly think of x is a big matrix。And y is also a vector。

 and the dimensions have to match ups。ok， so。You know， you can do some。那。You can do some。Well。

 actually I can just say kind of intuitively。But you can verify it by like computing a gradient and setting it to zero。

 So what is the beta that's the minimizer？Okay。😊，If you just think about it， well。For any beta。

 x time， what is the set of all possibilities for x times beta？Well。

 that's just the column space of x， right the set of all vectors of the form x beta is the column space of x。

Which Gelani is the are your dimensions reverse？あX。Oh for Wyoming or sorry for for W，2是。I mean。

 why is a vector， so it only it only has one。Okay。😊，So yeah， so let's just think about it。

 the set of all x beta is like the comm space of x。Which is a linear subspace of RN。Okay。

 so let's look at why， Y is a vector in Rn。And you can decompose y as like y is kind of y perp plus y parallel。

 like y is the part of y that's that lives in the subspace。

 that column space of x plus the part of y that's orthogonal to the subspace。Okay。

 and if you're trying to， if you're trying to minimize this alt2 norm， like the best you can do。

Is like entirely kill the part。Entirely kill the part of。Of why that lives in the subspace。

And then what you're left over with is just the norm of the perpendicular part。Okay。

 so basically you should choose beta such that x beta。

You want x beta to be the projection of y onto the column space of x。And， you know。

 you may have seen this in linear algebra you may not have this should be basically。呃。Let's call it。

 I don't know。The projection matrix aren't in the common space of x。诶。Okay， so actually。

 let me be that right。This should be equal to the。To the beta such that x beta is equal to the projection。

Onto the calm space of x。Of why。Right， that's what you want。And it turns out that， you know。

 that has a form that has something you can write down， which is equal to。嗯。X transpose x。

Sudo inverse。X， Y， I think。Okay， and if you don't know what the pseudo inverse is。嗯。

The pseudoinverse has a definition， so what is the pseudoinverse thing？Just a background。

If you have a matrix A。It can always be written as。U sigma v transpose。

 this is called the singular value decomposition。Where。U and V each have orthooral columns。And sigma。

Is some square matrix。Where the dimensions are both equal to the rank of。The rank of a。

And it's a diagonal matrix that has。See these numbers on the diagonal， which are strictly positive。

 So Sig 1 is greater equal to sigma 2 is greater equal to greater equal to sigma R。

These are called the so called singular values。So theorem。Theorem， any matrix。

 any real matrix A has an SVD， it can be decomposed in this way。ok。And then。The pseudo inverse。

Is just defined to be。V Sigma U inverse。ok。And the property that oh was sorry， not you sorry。

 that' that's not what I meant to say。V sigma inverse u transpose。That's the pseudoinverse。

And it has the property that， you know。If you look at。A A plus A a pseudoinverse。

 What is that equal to， that's equal to U sigma V transpose， V sigma inverse U transpose。Okay。

 V transpose V as the identity because V has orthonal columns。Sigma， sigma inverse is the identity。

Because it's the inverse。So this is just equal to。Uu transpose。

 which is equal to the orthogonal projection。On to the calls space of A。Right the columns of you。

 like if you look at the SD。The columns of U form an orthonmal basis for the column space of a。

And the columns of V。Form an orthonal basis for the row space of a。

So that's the one property of the SVD。So， you know， a plus is this matrix that has the property that。

AA+ is the projection under the column space。A plus a would be the projection onto the row space for example。

 so I mean， it， you know， it's called the pseudo inverse because a might not be invertible。

 it might not have full rank right or it might even be a rectangular matrix in which case doest make sense to talk about its inverse。

But this thing has some properties that are similar to the inverse， right， if you take AA inverse。

 you get the identity。Which is is the projection onto the column space or row space of a because it's everything。

m but in the case that a doesn't have full rank。Then a plus an A and AA plus still give you that projection property。

ok。😊，嗯。Okay， good。So。What should I say。Okay。So maybe now I'll just talk about something about runtime。

嗯。Right， okay， maybe also I'll say something about。This matrix here。 So if you look at。

 let me also just also take a second to look at this。 So if you look at x transpose x pseudo inverse。

Lets analyze what this is。What is x transpose x based on the SVD？Ex transpose。Would be。V sigma。

 you transpose， right。 So thatd be V。Sigma u transpose， that's x transpose。Times X。

Would be U sigma v transpose。So that would be equal to v sigma squared to v transpose。

Then when you take the pseudo inverse。When you take the pseudo inverse of this thing， you'll get。

V sigma minus2 v transpose。And then there's an x here。So if you multiply by x times x。Times X。

 let's say times X times X times X X is again。嗯。😊，I guess this should be probably be x transpose。

The x transpose will again be v sigma u transpose。Right， so this V transpose V as identity。

 this sigma cancels one of them， one of the minus two that makes it minus1。

And then now we want beta such that x beta as the projection of y。So if you look at x times this。

X times this。That's equal to U sigma v transpose。V sigma minus1 U transpose。

V transpose V is identity， Sigma， Sigma universeverse goes away。 This is U transpose。

Right so that's why we're doing what we're doing basically we're just using the fact that I know this looks like a mouthful。

 but we're using the fact that for any matrix X。If you look at。If you look at the matrix。X。

X transpose， x pseudo inverse， x transpose， Okay， so sorry if that looks like a mouthful。

This matrix is the projection onto the column space of x。That's just a general linear algebraic fact。

Did did we just say that was just X X pseudo indoor there， Like why do we need。Like the extra stuff。

A。I it to address Yeah， so， so I guess the issue here is。Oh， I mean， like why don't I just compute X。

 I mean， yes， I think I could have done the thing below as well。 Like， why don't I just do。Oh， okay。

 sorry， sorry， So I don't like， okay， so and let me back up a second。

I don't want beta to be the projection of Xon to y。

I don't want beta to be the orthogonal projection of y。

 I want X beta to be the orthogonal projection of y。😡， so if I choose beta if I choose beta then。

To be this。I in fact， get that。If I choose beta to be that thing。

 then x beta will be the projection of y。Does that make sense？Yeah。Okay。

 so now let me say finally something about subspace embeddings。 So we said that beta Ls is equal to。

X transpose x pseudo inverse， x transpose y。Now， naively with four loops， you know。

 what is x transpose x， This is a D by D matrix， right， because x is n by D， X transpose x is D by D。

So it has d squared entries and for each entry， how do you get that entry。

 you dot product the corresponding column of x with a corresponding column of x。

 so the IJF entry of this is like the I column of x dot with the J column of x。😡。

Which those are n dimensional vectors。 So it takes you n time。

 So there are D squared dot products here。 Each one is going to take you n time to compute。

 This naively takes。Oh of Nd square time。And that's what we're going to try to speed up using subspace embeddings。

Okay， so instead， sketching solve says。I'm going to sketch everything down to low dimension。

 and I'm going to solve it into sketch dimension。 So beta tilde Ls。

 I'm just going to define as being the argument。Over beta。Of pi X， y， pi x beta， sorry， minus pi y。嗯。

好去。Okay， so it's just like what I had before， but I threw pies into it。And for the same reasoning。

 this is going to be equal to pi x。Transpose pi X。Sudo inverse， pi X。Transpose pi y。

I know that sounds like a mouthful， but that's what it is。

 right just based on the same thing we said last time。And now what's the point。

 Now the point is this。It's not an n by D matrix anymore。It's an M by B matrix。 So this is O of。

M D squared time。Plus， the time。To compute。Pi at times x， right？

Because we have to actually sketch it down。So we want M to be small。

We're going to end up getting m to be roughly D or some D over epsilon squared or something。

 but we want m to be much smaller than n。And we also want a pi which allows for fast matrix matrix multiplication。

 so for example pi is sparse， so we're going to use something like the count sketch or sparse JL。

 or if pi has structure like fast JL based on the FFT， we can compute piX quickly。Okay。

So then the question is， why should beta Tilda LS be any good？Right。😊，Yes， we can compute it。

 but why is it good？plain。Let E be equal to the span of y as well as the columns of x。

Note now the dimension of E is at most d plus1。Then， if pi。Is an epsilon Subspace embedding？回忆。Then。

If you look at the performance of beta tilde， so pretend to use beta tilde， beta tilde。

 x beta tilda LS minus y。L2 norm squared is at most1 plus epsilon over1 minus epsilon times x beta Ls。

Mus while square。Does that make sense， so what I claim is if you do sketch and solve。

The beta that you get out。Is almost as good as the actual optimal data， which is beta Ls。

 So even though we're not solving for beta Ls。 we're solving for something different。

 it does almost as well for regression。Okay， and let's prove that。Fush。

So the first thing I'll say is if you look at pi。X beta tilda LS。Minus pi y。Ll2 norm squared versus。

Pi x beta L S minus pi y L norm squared。 So that's the difference here is 1 is beta 1 is beta tilta。

Which one is less than the other， Who's smaller。Any takers？

Beters tellda smallest'ca it's the like man。Are people still there are you frozen。

 someone type in the chat so I can make sure people are still there， hello。Oh your picture is frozen。

 but I can hear you。Yeah yeah， he's frozen to no， Yeah， I can't hear you anyway。



![](img/f6c71688f78e00ebac2311666589c956_6.png)

![](img/f6c71688f78e00ebac2311666589c956_7.png)

Okay， sorry about that， finally I'm back in， can people hear me？Yep。O。

So as soon as they asked the question。It seems I was booted。

 so let's go back to the question again Yeah， so the question was so I just give me a second。Yes。

 so right here， I claim that there's some inequality right here。One of them is less than the other。

 who's less than who？And why。I must say beta tilda because it is defined to miniise that quantity。

 Right exactly， right， Beta Tilde is the minir for the sketch problem。 So it goes this way。

And then now I can just say that this is equal to pi times something。What is that something？

That something is in the subspace E， right， It's a vector， which is in the column space of x。

Minus y y is also an E。 so that thing is an E， so this is at least。

1 minus epsilon times the norm squared of x beta Ls minus y L2 norm squared。

And similarly on the right， this is at most。1 plus epsilon times x beta Ls minus y L squared。

So you just rearrange things， this implies that。You know。

 take basicallyically take this and compare it to this。It means that x beta tilde。

LS minus y L2 norm squared is at most one plus epsilon over one minus epsilon times x。

So this is like a very simple application of subspace embeddings， right？嗯。And again， I choose。

 if I use it like an oblivious subspace embedding。That it doesn't， I should also have written。

 you know， there's also the time。Now， plus the time。's a find pie， right？

But if I'm using an obivvia subspace embedding， then it doesn't take any time to find pi or it doesn't depend on the input at all。

 you just choose it randomly。I want pi to be sparse or fast so that time to compute pi X is fast。

 and I want M to be small。Okay， so so this is a very simple example。

 we're going to see actually there's even more efficient ways。

To use subspace embedding for regression， even， you don't have to rely entirely on it being a subspace embedding that will get used M to be something like D over uppson squared。

There's a way to argue that combines some embeddings with。AMM。

 approximation matrix restricted the fromenience norm that actually will allow you to get away with deal over epsilon。

And in fact， you can even get away with M being roughly D independent of epsilon if you use subspace embeddings in combination with something like gradient descent orative iterative methods。

 so basically there what you do is，😡，You use Pi， you use a subspace embedding to help you find what's called a good preconditioner for your input matrix。

And then once you have a good preconditioner。That reduces the condition number of X so that gradient descent will converge in fewer iterations I know what I'm saying right now might sound like nonsense is I'm going to find anything I'm talking about。

 but you'll see that next week when we talk more about this so I think that's all I want to say for today Monday you're going to we're going to talk about how to get pie using sampling via leverage scores as well as how to get it via how to get obliivvious subspace embeddings and then we're going to see kind of more sophisticated uses of subspace embedding for regression for other problems as well like lower rank approximation like clustering。



![](img/f6c71688f78e00ebac2311666589c956_9.png)

So。