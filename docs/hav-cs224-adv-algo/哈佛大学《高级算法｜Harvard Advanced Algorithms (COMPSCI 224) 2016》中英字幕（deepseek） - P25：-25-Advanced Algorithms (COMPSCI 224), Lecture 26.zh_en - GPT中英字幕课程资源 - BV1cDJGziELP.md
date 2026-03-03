# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P25：-25-Advanced Algorithms (COMPSCI 224), Lecture 26.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/9c4472ae2165886fad9c55db9a042192_0.png)

可以。No， thanks。Okay， so I think I'll just on， okay， I'm going to get started。So today。Well。

 the last day。We're just going to。finish是。Streaming。And I'll。I'll just call today。

The power of random signs。So we're going to see。L2 norm estimation。We're going to see。

Fast regressioning。Point query。Mality reduction。So。It might seem like。Many things。

Some of the things I， well， actually is。All these topics covered in depth。

I do cover in depth in algorithms for big datata CS229 R。

 so I'm not going to provide all proofs here。But I wanted to give you a taste of。Some of this stuff。

Okay。So remember last time。Last time。We had a vector x， which was an RN。And it's huge。

And we wanted to compute functions of x。Well， x is updated in a stream without actually remembering the entire vector x。

So。Receive。Updates。Xi goes to Xi plus B。In a stream。And we must answer。Querries。T f of x。

So last time I said that V was always one。And it starts off， I should say， x starts as a zero vector。

So last time I said v is always one， let's say the query we want to answer is the support size of x。

That was the distinct elements problem。 I showed you that there's some non trivialvial algorithm if you assume some idealized hash function。

有人。So。嗯。Good， so what's a different。 but there are other functions that you might want to compute。

 other types of queries， so。Another F。Is F of x。Equals say。The L2 norm squared of x。

 or just say the L norm norm。If you can compute this up to some one plus epsilon error。

 you can compute the altoon norm up to some1 plus roughly epsilon error just by taking the square root at the end。

嗯。And the argument I'm going to show you is due to alone my taste and second。Okay， so。Just like with。

Support size。You can't get little low of space。Unless。

You settle for both randomization and approximation。 So you're not going to output the true answer。

 You're going to output the answer up to one plus epsilon。 let's say up to 1% error。

 and it's gonna to be a randomized algorithm that fails with probability 1% or something unless you allow for both。

Randomization。One approximation。And the AMSS algorithm introduces an idea that gets used all over the place in streaming algorithms。

And it's particularly important when V can be not only positive， but also negative。Okay。So。

If you think about the algorithm we saw last time where V was always one， in other words。

 V was always positive。You couldn't support deletions in the stream。

 right so the number of distinct elements is support size。

If I later wanted to delete an element that I saw， well。

 I'm only storing the minimum hash value I ever saw。

So if the item corresponding to that minimum hash value gets deleted， then。You know。

 my minimum hash value I'm storing is irrelevant now。

 and I don't know the second minimum because I didn't store that。 So what can my algorithm do。

So linear sketching， what I'm going to show you， allows you to design streaming algorithms that support deletions。

 so linear sketching。Okay， so it lets you。Support deletions。And in fact。嗯。

If you have to support deletions。It's known that essentially any algorithm can be converted into a linear sketch with at most a small blow up in space complexity。

 like a log n blow up in space。For any queryia。There's a minor space blow。

If you want to see the details of that。That's due to。Lgun。我。ううん。Okay， so let's go back to。

Back to the problem I stated。Back to。F of x being theeltime norm squared。So。

 so what is a linear sketch。 I didn't actually you can if you want can maybe I'll tell you now what the idea is。

 So the idea is you pick。Some matrix。Let's call it pie。Which is M by N。And you store。Y equals pi X。

In memory。Okay， so。Initially。Let's say y is0。Right because pi is 00。 And if pi looks like this。

 so pi is some。Thatat。Short matrix， let's say the columns are pi 1。Up to pi N。

And let's say this M dimensional has M roses。If I see an update。Where I add V to X I。

 what does that imply I have to do for my streaming algorithm， that implies that y。

Should be incremented as follows。 Why should become。呃。呃。Y plus。V times pi I。对。

So I can support arbitrary updates in the stream just by updating my linear sketch like this。

And this holds whether or not， whether I have deletions or insertions。

So what's the linear sketch going to be for RFf？We'll pick pi Ij。To be plus minus1 over root M。

Uniform。So let's say it has independent entries and each one is a random sign over RuM。

And now we have to estimate。We have to estimate f of x based on the y we have in memory。Right。So。

 we'll estimate。The al norm squared。As。Just the alum squared of y？Okay。And let me just。

 I want to call this random sign Sigma IJ from now on just when I get into the analysis。Okay， so。

Why does this work？So the way that many algorithms get analyzed in streaming， including this one。

 is to first， you know， basically bound the expectation， Bo the variance。

 and then use chubby ss inequality。So。Let me show you that。So， the expectation。Of y Uin norm squared。

That's equal to so here's my analysis。嗯。Well， actually let me before I say that。

What do I want to say， I want to say， look， the probability。That。Y L2 norm squared minus。

X L in r squared。What's the probability that this thing deviates by more than epsilon times what it should be？

I want to say this is small。 I want to say that it's at most a third or something。Or 100th1。

 you know， my my probability of failure is almost 1%。 And by the way， what does this say。

 This is the same thing as saying that。Y L2 norm squared is1 plus or minus epsilon。

Which is what I want， I want to get the answer up to this one subpsilon error。

I it clear what I mean by this notation， I mean that it's at most one plus epsilon times this。

 and it's at least one minus epsilon times this。Well， this thing。This thing is at most。

 the expectation。Of。Y L2 norm squared minus the expectation of minus x。Elson norm squared。Squareed。

Over epsilon squared times L2 norm to the4。This is chreubby Sheev's inecality。Yeah。

Which is just Markov after you square things。So we just need to understand this expression up top。

So first of all， I want to say that this Lton of x squared。Is just the expectation of that。So。So。

 the expectation。Of y L2 norm squared。So that's the sum over I。Let's say R from 1 to M。

Expectation of Y squared， YR squared。That's just linear of expectation。So。

I want to understand what is this quantity here？For any fixed star。They're all the same for all art。

So what is YR， YR is just。One over。Ro n。드라이。What is my definition of pi I J， Its this， right？

So yr is1 over a root M。S I from1 to n。Of Sigma R X。Which implies。That yR squared。Is 1 over M？

Some over。I from1 to n。Sigma R squared， X squared。Plus sum of I not equal to J。Sigma R， Sigma Rj。

xi X。So this implies that and this thing here is just one。

So this implies that the expectation of YR squared。Is1 over m U of x squared。

Plus some I not equal to J。Expectation， Sigma R I， Sigma RJ。X Xj。But if these things are independent。

 this is equal to expectation of Sigma R。Expectation of Sigma Rj。Which is just。0。

So this thing goes away。So this implies that。Expectation of y R squared is1 over m times L squared of x。

Which implies that expectation of y squared。Which we said was。One over which was sorry。S over R。

Expect YR squared is just alternate x squared。Okay。So we know that this thing here。

Is just equal to now the variance。Of this random variable。Over epsilon squareer times。X to the。

We just show that thing is the expectation。So that is the definition of variance。And if this matrix。

The entries of pi really are independent。Then that means that。The entries of Y are independent。Right。

 so。Now let me say what I want to say， so the variance of this thing。Is the variance of。

The sum over R from 1 to M。Of Y R squared。But if you have random variables that are independent of each other。

Then。The variance is just add。So this is equal to。Some。R from1 to M。Of variance。Of Y ared。So。

Let's bound this thing。So。Vance。Of y R squared by definition， is what it's the expectation。Of。呃。

YR to the fourth minus the expectation of YR squared。Squared。And we just said this thing is。

X L2 norm to the fourth。How about this thing， sorry， and there's a one over。M squared here。Right。

Yeah so I just squared this thing。So how about this？Well that we can expand out。So。嗯。

What's YR to the fourth？We wrote what YR is， so that's 1 over M squared。Times。A sum。I equals 1 to n。

 sigma R。Xi。To the fourth。Okay。So。We want the expectation of this thing。

So you can imagine expanding this thing out to the fourth。And having lots of monoials。

 roughly end of the fourth monoials。Or exactly into the fourth monoials。

And then you can use linear of expectation to push this expectation inside。Okay。Some of the terms。

So what are you going to have， you can have some terms which are like Sigma R for some I to the fourth power。

对。Or you can have two different indices， I and J， and you can have Sigma R squared and Sigma RJ squared。

 You can have Sigma R cubed and Sigma RJ to the first power。 Basically。

 these powers have to add up to four。Right so let me。Let me just write this explicitly。

What over m squared。And then， expectation of。Some over I。Sigma R to the fourth， X side to the fourth。

Plus sum over i not equal to J。Sigma R squared， Sigma R J squared， X squared Xj squared。

Plus sum not equal to J。Sigma R cubed， Sigma Rj， X cubed。J。Et cetera， right。

 You can also have three different indices。Two of them get raised to the first power。

 one gets squared， you get lots of different things going on。Now。

 when you push this expectation inside， let's look at， for example， this monomial here。

I should be clear there are more things here that I can write。Well， first of all。

These two things are independent of each other。So the expectation of their product is the product of their expectations。

And the expectation of a sign to an odd power is zero。So whenever you have any odd powers。

 the terms just disappear。 So this is similar to， I think， way back。

 I had you prove the turn off bound。Us。Well if I explicitly。呃。Writing down all the monoomials。

RightSo it was the same thing there that things with odd powers disappeared。

 so the same thing happens here。And basically， the only things you're left with。

Are terms like this and terms like this。 Everything else doesn't matter。Okay。

So this thing I claim is just。1 over m squared times。You have this term。Some over I。

X side to the fourth。Plus， you have the other term some I not equal to J。Xi squared Xj squared。对。So。

Conveniently。呃。That channel high square。Right。So this thing here。Is at most some over I X I squared。

Squared， which is equal to x2 to the fourth。So when you subtract out this thing。

 you're subtracting this out。The overall thing is negative。I should be。

 should I be a little bit more careful？Right， oh， yes， yes。 good。 There's a constant here。

 which I completely didn't write。 Okay， good。 I was like， this is a little too good。Yeah。

 I think it's because I wrote I not equal to J。I think it's three。No whatever。

 there's some constant here。It's not so。Weren't。But。Okay， so now overall。

 this implies what would we have that the variance。Of。Y R。Squared。Oh， and actually。

 if I can even be a little more， I can optimize things a little bit more。

 Let me me not let me not do this。 Let me just。Keep it like this。And let me say this is equal to。

1 over m squared。This is a constant factor， it doesn't really matter。X2 to the fourth。All right。

 most。No equal。Plus 2 some minus not equal to J X I squared， x J squared。

When you take one of these and add this in， you get exactly this and then you have this here。Okay。

 great and then now。Conveniently， this thing。Cancels that。So the variance of y squared is at most。

Two times。呃。This sum over I X squared squared。Which ist。Does a division by m squared？

Which is2 over M square。Times。So。Expectation。 Oh， so， right。

 So I said that the expectation basically kills all the terms of odd powers。

And then terms of even powers。嗯。And a random sign squared is just one， so the randomness disappears。

So what we just showed is that， well， the variance of the sum of all of those。

 so the variance is at most2 over m times x2 to the fourth。I'm sorry。But I summed it M times。Yeah。对。

And we said that the probability that we failed， that was what I just erased here。

 the problem that we failed was that most this quantity， which was this。So this isn at most。2 over M。

Times。X2 to the fourth。This is the variance。Times1 over epsilon squared times x2 to the fourth。Right。

This thing is gone。So if we want this to be less than， say， a third。Well set。A to be something like。

Six over epsilon squared。So that this is less than a third。Okay。Sorry。There's an M squared。Where。

But it's the variance of this， which is that。Yeah。Okay， great。So the conclusion。Oh， you're scbing。

 right， is it？呃。If we use like one of Rpson squared words of space。Our estimate。

Is one plus or minus epsilon times。Elsson norm squared with probability， at least2/3。

One thing you can do to amplify this。Is just repeat this same。Basically， let me。You know， to get。嗯。

With probability， at least one minus delta。What you can do is。A common trick。Basically。

Your linear sketch will be the concatenation of many independent copies of this linear sketch。

So you'll have pie up here。Which has。You know one over Epsilon， the six over epsilon squared rows。

And then you'll have another pi prime down here。Which has。Six0repsilon squared rows。Okay。And。

You'll have， you know， K being something like。Log whenever Delta。Independent。Coopies。Of pi。

So it implies you all。Obtain。K， independent。Trials， let's call them y1 up to YK。And the algorithm。

We'll estimate。W k。All right， we'll estimate。XL norm squared。As the median。Of of all these things。对。

Why does that work well the point is。Each one we know works with probability2/3s。

And for the median to fail。Strictly more than half of them have to fail。

RightBut we know that basically the expected number that worked for us that give us a good estimate is k times 2 third。

And we fail with this procedure if the number that work is less than k over 2。

So there has to be a significant deviation from the expectation in terms of the number of trials that worked。

And by a turn off bound。The probability that we get that kind of deviation decays exponentially in K。

And exponentially in K means like one over exponential in K is delta， basically。So。

Expected number of trials。Succeeding。Is。Is at least two third of them？We fail。

If less than k over a two， succeed。Probability that less than ever2 succeed。Is exponentially strong。

This is turnoff Fo。Sure。Okay。Now。So great。 So we know that。Ilies space。Let's say。

1 over uppsilon squared log1 over delta。For success probability。One nice so。And it turns out that。

This is optimal。So， I mean， there was quite a long line of work showing that this was optimal。

 I mean， initially。People couldn't get the winter Robsson squared， but they couldn't get the product。

Well even before that， people look at one over Epsilon， but not one over Epsilon squared。

 there's quite a chain of papers， I'll just cite the most recent which finally gets this。

 which is due to JRAM。Wdr。This is transactions。Well， that's a journal version anyway。Okay。Right。

So there are many things that I wanted to show you that was。Elitude on estimation。

One thing I wanted to say is， so I guess here you already basically see it from the proof。But。

You know don' you're trying to get a low memory algorithm and this matrix pi。

 the number of columns of pi。Is N， right？So if you actually were to store this pi。

 you'd use more space than storing X by itself。Right， which you don't want to do。So what do you do？

Well， you look at the proof and you say， look， when I calculated。I needed to calculate the variance。

 and I need to calculate the expectation when I did those things here。

AndSo I do calculate the expectation of this thing and then the expectation of this whole thing。

If you expand this thing out。You get at most kind of degree four polynomials in these random signs。

And we only needed to be able to say that the products of those four things behaved independently。

RightThose four things are independent。 So we just need four wise independent random signs。

And we saw earlier in the course that you can generate fourY independent random signs using kind of log n bits。

 a hash function specified by only log n bits， a fourY independent family。

So this entire matrix pi really。Well， each one of these things stacked only needs4Y independence。

There are log1 over delta of them， so the total space is log1 over delta times log n。对。

So this whole matrix， this entire thing here， is specified using very little space。

So login bits is like a word。 So each hash function for each one of these only needs a like a constant number of words of space。

 and there are login Dta hash functions because you're repeating this login Delta times。

So log1 else are words。Okay so that's really， I'm not hiding anything。

 that's really the entire analysis of this。嗯。Actually， maybe I'll。Before I move to the next board。

 let me just say you one thing。Space。the space is this， but how about the update time？

I said that streaming algorithms are basically small space data structures and data structures we care about space。

 update time and query time。And dynamic data structures。

So what's the ignoring a time to evaluate the hash functions， which are。

 which is constant anyway with the right hash functions。What is the update time in this algorithm？

If you see a new update in the stream， how much time does it take to update your sketch？

I guess the hint really should be right， when you see an update， this is what you have to do。

 you have to add this into your sketch。Order M， right？Which is。Which is this。So the update time is。

Also， when I rhsson squared， log whatever delta。And the reason for that is that when you're adding in some multiple of。

 you know， a column of this matrix， this is a completely dense matrix， right。

 Every single entry in this matrix is some random sign。嗯嗯。

So you have to touch every entry and why to perform an update。So， one way of。One way of。

Improving that。Is to make this thing sparse。And in fact， you can do that， so Thor and Zhang。嗯。

Let me not say the journal version because I might get the year wrong。

 but the conference version is soda 04。They just look at。Pi being as follows as。This is again。

 theta when of rhpston squared。You have n columns。And what's your matrix in each column？

You pick a random location。And you put a random sign there， and the rest of that column is zero。

And each column looks like this。Your other column you have。A random location。

 you put a random sign there， everything else is here。The rest of their algorithm is the same。

You maintain y equals pi X。And your estimate of the Ln norm squared of x is just the Ln norm squared of y。

And you basically can show the same exact thing。You can show that the expectation。

I'm not going to do it on the board。The expectation of y squared。Is still x squared。And the variance。

Of y squared， you can show。Is still。嗯。O of1 over M times x2 to the fourth。That's a computation。

Not very different from。The computation you saw， which implies that you can use this sketch instead。

对。No。Yeah， so this is just strictly better。And you can do the same thing where you repeat this log 1 over delta times。

 take the median。 So this。Has update time。What's the update time for this if you want success probability1 minus Dlta？

啊。Yeah， law whatever else。Okay。So you get rid of this 1 orson squared in the update time。And。

It's actually an open problem that I myself am quite interested in as to whether or not you can do better than this。

Okay， is there an algorithm that achieves success probably one minus delta for L2 norm estimation。

 which gets the right space and gets update time， which is say constant， why not。Or。You know。

 root low wealth or something。So we can show something。 We can show that if you use a linear sketch。

The update time has to be roughly root log whenever over Delta。系。But。

there's a gap there between log Win Delta and log Win Delta。Okay。So that's。That's L norm estimation。

Questions about it。Okay， so you might ask， you know， motivations of this thing。

 Where does it get used， So， for example。嗯。I can tell you where at Thorpe and Jng were using this thing。

So both of them were at A T and T research， which， you know， A T and T has lots of routers。

 and again， their， they're vector X N is the number of you know， destination I addresses and X I。

 They didn't even care about deletions。 X I is just。

How many packets did that destination receive over some time window？

And you know the thing about the Ltin norm squared is that it measures。Kind of spikes。Right。If。

I mean， the thing that measures spikes the most is the infinity norm。RightIn terms of。

 is there an entry I such that X I is very large。You really want the infinity norm and that will tell you what's the largest Xi。

It turns out that unfortunately， there is no efficient space efficient streaming algorithm for the infinity norm。

But the largest value of P for which there is a space efficient algorithm for the LP norm is P being 2。

Okay。I'm not going to justify that， but it's known people have proven that。

So they were looking at that to basically estimate skewewness in the distribution of packets going to various places。

As part of a system for detecting denial service attacks， and they really cared about。

A faster algorithm because this thing was sitting on the router right。

 and network speeds are really fast。 they can't afford to spend， you。

 let's say you want 1% error on your estimate。So one of uppsson squared is 100 squared， which is 10。

000。 So basically they just got rid of a factor of 10，000 in their running time。

 which was very important for them。Okay， so good。So that's L2 estimation it gets used in other places as well。

I mean， one thing I can mention is。You saw in one of your PSsets Jaard similarity。

 where you wanted to estimate the similarity of two sets。

 and you used the min of a hash function to do it。Another way of estimating similarity of。

 say documents。I think in the piece that I mentioned the history with like web pages。

 estimating similarity of web pages， right， Another thing you can do to estimate similarity of web pages。

Is cosine similarity。So for example。Xi is number occurrences。Of word I。In document X。

And you normalize the document wait so it's normalized。And what I mean， normalized， I mean。

 once you define this vector x， you normalize it so that it has unit norm。

So then now you have a bunch of documents， right。So x lies on a circle， you have one document x。

You have some other document why？You have another document Z。Et cetera， how do you estimate？

The similarity of two documents using cosine similarity， well。

 it basically comes down to the angle between the two documents。If the angle is small。

 you say the documents are similar。And how can you use this kind of。Streaming algorithm。

To estimate cosine similarity。Well， forget about streaming。

 just think of it as a method of compressing the document。Instead of storing the document X。

 you'll store the compression pi X。This compression is often called a sketch of X。And。

You really want。You really want Xy， which is say cosine of theta。

So you want to know some information about， right， cosine of theta。嗯。Is large if theta is small。

 right， It's one if theta is 0。You really want to know this dot product？

And what you'll do is you'll estimate。As pi X。Not py。对。Where pi is exactly the same pi。对。And。

You know， you can do an expectation variance analysis to basically say that this works。

 It'll give you an additive epsilon with probability 1 minus delta to the true dot product。

By redoing this， or you can just say， look。You can say。Pi x。Minus。Pi of x minus y。Squared。actually。

 let me just write it like this。A minus b squared。Is a squared plus b squared？Minus2 a dot B。Right。

That's just an identity。Which implies that A dot B。Is equal to。A squared。Plus， B squared。

Minus a minus b squared。Over two。And what do we know about pi。

 we know pi preserves L norm squares of vectors。Right， so imagine imagine that A is now。

Pi X and b is pi y。We want to understand what does pi X do pi Y look like。Well。

 it's pi Xl to norm squared， which is roughly Xl to norm squared。Plus pi y2 normm squared。

 which is roughly y2 norm squared。Plus pi of this vector and some other vector。

But pi preserves norms of vectors， so it's roughly what it should be up to this epsilon error。

So the fact that you preserve L2 norms of vectors means you preserve dot products。

 which means you roughly preserve cosines of angles。

So you can use this same exact setup to do cosine similarity， right？Does that make sense？Yes。

 let me show you。Some more power of random signs。Another example。So let's say statistics。

Such as linear regression。Right。So the idea here is。We theres some。Pararameter。Vectctor。X and RD。And。

Given variables。A1 up to 80。呃。Our system is linear。And you know， we should have that B is some of。

I equals 1 to D of AI Xi。So。There's some other variable in our system B。😡。

And it behaves as a linear function。Of other variables， AI。

And the coefficients of that linear function are these Xs。And we're imagining we don't know the X's。

So we're doing experiments。And based on our experiments， we know a lot of AIs。

 We know the resulting B。 We can observe all these variables。

 but there are some hidden variables Xi that we don't know。And we want to solve for them。

And the way this is done is write you write a matrix A， which is。Really。

 this thing was tall and skinny。A one。two。Again。So it's an N by D matrix。And。You want。To find。

X such that。 So let me call this。You know， be。B one。So that AX。Is B。Or B。B is also this ndial vector。

Now， usually when you do linear regression statistics， just the show of hands。

 some people have heard of linear regression。So usually you assume that。

You don't actually observe the true variable， but you observe the variable plus noise。We observe。B。

 which is。A sum of I plus1 to D AI Xi。Plus， noise。Noise in our experiment。

 or there's some noise that's generated as we do this。

So we want to find x such that Ax is approximately B。Okay， so to be specific。We want to compute。

X star， oh， you had a homework on this as well。 So you want to compute X star， which is the argument。

Of A X minus B。 So yeah， I guess everyone should have heard of at least where's Russian unless you drop that piece set。

Okay。Good。嗯。As we， I guess almost saw on the Pet， you can write that X star is equal to。

A transpose a， pseudo inverse， a transpose B。So in the piece that I think I said that a has full column rank。

 in which case the pseudo inverse is the inverse。嗯。I don't want to get into， you know this is。

The pseudo inverse， basically。It's some generalization that also lets you handle the case when it's not full rank。

 you can go look it up if you want。 It's not going to be important for what I say。

The thing that is important is。How long does it take to compute a transpose a？N squared， right？Oh。

 n squared， not n squared。 So A is n by D。N times d squared， actually。

Because so if you look at a transpose a。A transpose a is a D by N matrix。Times an n by D matrix。

Right so you have to keep doing these dot products。Like this。Okay。嗯。Right。

 every time you want a compute an entry。 So the resulting matrix should be D by D。Right。

 so for each one of these entries， you have to take one of the rows here and a column here and take a dot product。

 So that's end time。 And there are D squared entries。 So this implies。N times d squared time。

And that turns out to be the bottleneck。 The pseudo inverse takes polyd time。

 like roughly D cube time。So the bottleneck really is doing a transpose。I mean。

 another way of solving。As you saw in the PSet。嗯。Another way of solving this thing is using gradient descent。

 you start off with a decent solution， and then you keep refining it using gradient descent。

Well let me stick to this for a second。So。Can we speed this N D squared up using？

Using this Thor jog or using the AMSS sketch， this random science sketch。Yes， we can。

So let me make a definition， so Sloche。He says that。Pi。Is in。Epsilon subspace embedding。For us for a。

Sspace。V， a linear subspace。If。For all vectors v in capital V， we have that。Pi V L2 norm squared。

Is one plus or minus epsilon？好错好错。Okay。Okay。So it's sort of like know what we were talking about。

 preserving L2 norms squares of vectors， but there are like infinitely many vectors here。Okay。So。

Plaim。If pie。Is。An epsilon subspace embedding。For which subspace the span？Of B。

 as well as the columns of A。Then。If you look at。X tilda star， which is the argman。Of。

Pi Ax minus pi B。It satisfies。That。A x til the star minus B。

Is that most one plus epsilon over one minus epsilon？AX star minus B。

So Ax star minus V is the best you can possibly do。😡，And what I'm saying is， if instead， you use。

This as a substitute for the true optimal vector for regression， you'll do almost as well。

And what's the benefit of this， What's the algorithmic benefit of this？So。I should say here。

 hopefully。M is much less than n。 So this is an M by N matrix。So what's the benefit？So I mean， yeah。

 you do reduce space， but you also reduce time， right the bottleneck here。Was computing a transpose。

Which we said was Nd squared。But now we don't have to compute a transpose A。 Basically。

 a is now pi a。So pi a transpose pi a takes Md squared time。So if M is much less than N。

 we just replaced an N and within M in the running time。 And it turns out we're gonna see。

You can get M to depend only on D。 It doesn't have to depend on n at all。

So you you got a running time at the end of the day， which。This n becomes something function of D。

So let's just prove this。So first of all。X till the star is the optimizer for this regression problem。

 which means that。Pi A x t the star minus pi B。 I'm going to drop L2 norms or all L2 norms is that most。

Pi a x star minus pi B。Because I said X to star is the optimal vector for this regression problem。

And what is this， this is just pi。Times a x till the star minus B。This vector lives in that subspace。

 it's spanned by B in the columns of A， so it's preserved。Same thing here。

 This thing lives in the subspace， so it's preserved。That's it， now you just move this over here。

Proions about that。第二。Yeah， so okay， good。 So I slightly cheated。

 I said everything is great because now this n is an M。

 but I ignored that you have to actually spend time computing pi times a。Right。

But as we're going to see， you can choose pi to be like the Thorb Jg sketch。

And then pi is like super sparse， So pi A is really fast。So now how do you get the pies good。

 so you were asking about。How do you multiply at pi times a？So benefit。Bottleneck。For computing。

Ex tell the star。Is。Pi a transpose pi a。And this takes time。Okay， but as you said。

 what about the time？To compute。Paai。Well， to answer that， I have to say what is pi？哎。Okay。Yeah。

 was everyone。Still with us。So let's think about what it means to be a subspace embedding。Let's。

So what？Does it mean？To be。So space embedding。So let me say that。 So V is a linear subspace。

 Let's say the dimension of V。Is deep。So every subspace has a basis。😡。

And we can take an orthoormal basis。So let's say that u。Is an n by D matrix， the columns of U。

For an orthonormal basis。For V。Which implies that， for example， u transpose you as the identity。

What are what's the IJ entry of U transpose U iss the I column of U do with the Jith column。

So that's only since it's north thermal basis， that's one when equals J and it's0 otherwise。哎。嗯。Okay。

 so the definition of being subspace embedding is that for all V and V。Pi V。

Llitude norm squared is one plus or minus epsilon。嗯。V L to norm squared。But what is？What is V？😡。

V is just the set of all vectors， U UX。Where x is an RD。Right it's linear combinations of。

Vectctors in my orthonnal basis。So this thing。嗯。This thing is the same as saying。For all。X and RD。

Pi UX。Is one plus or minus epsilon？UX。But what is UX de norm squared to this is x transpose u transpose UX。

And you transpose you as the identity。So this is the same thing as1 plus or minus epsilon L norm squared of x。

So what we're saying is that all the singular values of pi U are between one minus epsilon and 1 plus epsilon。

2。The squared singular values。So this is the same thing as saying。All eigenvalues。

Of pi U transpose pi U。Our 1 plus or minus epsilon。

Which is the same thing as saying that the largest， the largest eigenvalue and magnitude of。

Tiu transpose。H you。Minus the identity matrix is less than epsil。Okay。Questions。

This is the operator norm， which means take the largest eigenvalue in absolute value。

 take the absolute value of the largest eigenvalue。And if you think about it。

Pretend that pretend that U was not a matrix， but it was actually a vector。 Pretend D was one。Okay。

If D is1， what is this thing here， this is just the squared norm of pi U。Okay。Meanwhile。

 what is this， This is， let's say， let's say U has unit norm。 This is U transpose U。

 This is a square norm of U。 So this is a squared norm of pi U。 This is the square norm of U。

And if you is a vector。Then these are just scrs。😡，And operator norm is the same thing as absolute value。

So this is like a generalization of what we just saw preserving vectors。

 instead of preserving vectors， you're preserving orthonormal matrices under operator norm。

So you can think about basically doing the same exact proof。Right， do chubby chefs inequality。

 the probability that。Pi u over pi pi U transpose pi U。Minus the identity bigger than epsilon。

Is at most the expectation。Of pi u transpose pi u minus identity squared。Over epsilon squared。

What is this thing？This is the largest eigenvalue squared。

The largest eigenvalue squared is definitely at most the sum of each eigenvalue squared。

Because when you square it， everything's not negative。So this is at most。

The expectation of the trace。Of pi U transpose pi U。Minus the identity。Squared。Theres on square。

The trace is the sum of the eigenvalues。The operating room is the biggest secondigenvalue。

When you square a symmetric matrix， the eigenvalues just get squared。

So this is the sum of the squared eigenvalues。 This is the largest eigenvalue squared。

 So this is definitely bigger than this。So this is like the matrix analog of what we saw before。

And I'm not going to do the computation。 But what you can show is that this thing。

Is one over epsilon squared times。O of d squared over M。

So as long as you choose M to be d squared of rhpsilon squared。You're done。If you use。

 say the Thorpe Z。Sketch， this matrix。This matrix where you have one non zero per column。Okay。And。

 you know， this thing is due to， So Clark and Woodrff had some。

They had a more complicated way of doing it that got a slightly worse bound。

But they were the first to do it。And then basically， this sequence of inequalities I just showed you。

Is。From。Mahoni and Meng。In the same conference as well as myself and Hu。对。

So now if you use the thb jong sketch。How long does it take to compute pi a？



![](img/9c4472ae2165886fad9c55db9a042192_2.png)

So pi。Has one non0 per column。And zero is everywhere else， and then you have a here。So。

So you can prove that this thing is basically the support size of A。And the reason。Right。

Our question。All right。嗯。Yeah， so let me just say what's the reason。

 basically think about a column by column。And for every non zero entry of a。

A non zero of A means you add the corresponding column of pi to your sketch。

But that column only has a single non zero entry， so you can do that in constant time。

So for each non0 and a， you're spending only constant time。To add into pi A。

Maybe you can think about that offline。So there's that。I showed you this and this。

How about point query and dimensionality reduction， maybe I'll actually switch the order of those。

And so now I just want to show you basically applications of。This pie， okay。

 that's what I'm showing you over and over again in different areas。So now I'm doing this one。

The idea here is there's this John Salin and Strauslema。It says that for all points x1。嗯。

Let's say for all sets x and Rn。Let's say that the size of x is capital n。There exists a matrix。Pi。

 what do you know。Where M is o of 10sson square root log， the size of x。Such that。嗯。For all X。

 Y and capital X。Pi x minus pi y。Is1 plus or minus epsilon x minus y。

And as I formulated where you want to use all in your sketch。It's known that this is optimal， so。嗯。

M being omega。Well， let's say the men。Of n and1 arerupson squared log n。Is necessary。

In the sense that there exists a set of vectors， capital X that really needs this number。

 this target dimension。Why did I have to put a min of little end there？Just around the same page。Now。

 I mean， I could always take pi to be the identity matrix。Okay。

 so you're not gonna prove that you need， you're never gonna prove that you need more than little n dimensions。

 but we can show that you always need the min of n and this。

 which is basically the right thing because it says that you should use this until the identity matrix is better。

So how do you prove this thing？Design a distribution。Such that。Let's call this D。Over matrices。

Just like we design distributions over pies。Such that。For all X and Rn。Of unit norm。

The probability over pi drawn from this distribution B。That px。Actually。

 let me call it Z because I don't want to conflict with that X over there。Probably that pies Z。Mus1。

Is bigger than epsilon is at most Delta。Suppose you could design such a distribution。

If you could design such a distribution。You would set Delta to be1 over， basically。And choose two。

Where capital N is that capital N？Set Z to be some。X minus y over the norm of x minus y。

We're excellent y R in this capital X。So。What you're telling me is this random matrix pi。

Preserves this vector。With high probability。Right。So by a union bound。

 it preserves all of these for all choices of X， Y and capital X with， with good probability。

So you're done。So what do you think pi should be？Random sign matrix，😊，Cosedi。😔，To be uniform。

Over random s matrices minus1 over rudeM，1 over rootM。M by N， matrices。We're M。

Is going to be1 over Epsilon squared log1 over Dlta。

So this log oneta is why you get a log capital line。I have some time。Okay， and。

I'm not going to show you the proof， why does this work if you choose M to be like this。

 but I'll just say it in words。So just now， when we looked at the streaming application。

 what did we do， We did chubby Cheevs inequality， right。Maybe I'll just write a little bit。

And the idea is just like in your homework， where you analyze the turn off bound using moments。

Instead of chubbyev's in equalityality， which means the second moment， you take a really big moment。

And if you take a big enough moment， you can get the error probability to be deelta。

So if you go back to your PSAT for the turn off bound。You'll find that if you wanted。

The right hand side of your final tail bound to be Delta and the turn off bound。

 the moment you ended up choosing was like log1 over Delta。

So go back to your solution and look at why that's true。And it's the same thing here。😡。

You end up basically just analyzing exactly what I showed you at the beginning of lecture。

 but instead of taking a second moment， which is chubby's inequality。

 you take the log one of adult moment。Okay， and you could do a computation that's a little heavier than what you did in that Pet problem。

 There are also like much simpler ways of doing it。 but in principle， you know how to do it okay。

Okay， so that's the dimensionality reduction in the very last minute。That's point query。

That's another streaming problem。Again。Xi gets updated as Xi plus V， this is streaming。

And then we have a query。FI， now there are many query functions。 F of X should be X。

So people can query what is the Ih entry of x？And again， we'll settle for。Approxiation， we won't。

 Yeah， we'll settle it for approximation。 So we're allowed to output X I plus or minus epsilon times the norm of x。

So we're going to use a sketch matrix pi as usual。Suppose we had a pie。Again， M by N。Such that。

If you look at pi being。Pi 1 up to pi n。We have that， first of all。Pi I。Has unit norm。And for all。

 I not equal to J。Pi I dotted with pi J。Is that most epsilon？So our sketch as usual。Sketch of X。

Is pi X。 Let's call that Y， and we estimate。X I。As。Pi y， pi transpose y I coordinate。

 which is pi transpose pi x。I have coordinate。Now， notice that。Let's call this。X I tilde。

And notice that X tilde。Is just if you go with this thing here。This is。

X I plus the sum of j not equal to I。Of X J。Pi I dot pay J。In general， pi X。😡。

Is just the sum over J of pi Jxj。When you do a matrix times a vector。

That's just a linear combination of the columns of that matrix。So this is what that is。

 but these things are all plus minus epsilon。So this is X plus or minus epsilon times the l norm。

So the only question is how do you get such a matrix？How to get such a pie？Apply the JLlema。

Johnnmon Strauss。To x being0 and then the n standard basis vectors。

Which implies that the number of rows you need is one of Repson squared login。No， and。I should say。

 where is this from？Right， and the point is。Look， as we saw。

Preserving L2 norms means roughly preserving dot products， right， because I had this identity。

 The norm squared of a minus B is the norm squared of a plus the norm squared of B， etc。So。If you。

 if you preserve distances between these vectors， it means you're preserving dot products between them。

But the dot products between all these vectors is zero。So you're preserving it up to Epsilon。

 that means the new dot products aren' at most Epsilon。That's that。And。

You're preserving the distances of these vectors to 0， which just means their norms。

 Their norms were originally one。Now there norms that are going to be roughly one。

 they're going to be one plus epsil under something。

But you can normalize them to make them actually one。 And that won't really change this by much。都在这。

对。So。There are many more ways to use random side matrices。That's all I can fit into。Okay， so， yeah。

 thanks。 And please have some before。