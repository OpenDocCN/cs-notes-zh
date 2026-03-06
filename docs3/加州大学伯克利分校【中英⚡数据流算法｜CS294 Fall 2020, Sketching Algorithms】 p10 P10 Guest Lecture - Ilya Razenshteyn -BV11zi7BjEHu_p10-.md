# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p10 P10 Guest Lecture - Ilya Razenshteyn -BV11zi7BjEHu_p10-

嗯。

![](img/8ac5e5dd26af7eedb4c26f21026d3061_1.png)

hi everyone， so today we're having a guest lecture from Elot Roznstein who's joining us from Microsoft Research in Redmond before I hand it off to him。

I just wanted to say some logistical things I did release problem set one this past weekend you can find it on the website you do need to enroll in the grade scopepe to submit everyone should have gotten an email with the enrollment code for gradecope if not please send me an email second thing project proposals final project proposals are due October 28th which is。

In a little over three weeks， you are allowed to do these in teams。

 go to the course webpage for instructions on how to prepare your proposal and submit them。

 if you have some questions， feel free to come to my office hours or if you can't make those set up a time with me to talk about what you're thinking about for the project。

And now we're going to have Ilia talk about a result of his from a few years ago so we've talked about sketching and streaming various norms like E Euclidean norm and other LP norms Ilia is going to talk about a pretty general theorem that relates embeddings and sketching for norm spaces so thank you Ilia for joining us today thanks Gni for the introduction so as Gi said I will talk about our paper that we had a few years ago that shows that basically norm dedimensal norm is has a good sketch even don't leave it nicely embeds into a certain sufficiently simple space。

so。Even though Gelani asked me to present like as much proofs as I can。

 I will not be able to show you all the proofs， but I will show you a proof of like big chunk of the result。

But before I' talk about the result， let me briefly。

 even though you have seen some streaming and sketching in this class。

 let me briefly reintroduce it tailored to this specific lecture。

So let's briefly free recall what is sketching， so you have some metric space。

Which can be finite or infinite。 So it's basically some set X equipped with some distance function disback。

And we basically would like to solve the following communication problem we have Alice and Bob。

 each of them have both of them have a point from our metric space and then they would like to talk to each other exchange as bits of information and later decide whether。

Points are close or they far。 and basically， they know a priori that either the distances at most one or the distance is more than capital G。

And they would like to tell apart these two situations。

There are like a few subtle points in this model。 So for now I just introduced it in a fairly handw way。

 but there are like a few important things that are important for for the result I'm going to talk about。

 but we will not be like basically。Yeah it will not be super important for the lecture but it is important for the result so basically the nuances of this model are what coins do we allow and how many of them so basically if the protocols are randomized and we allow randomized protocols because they are more powerful and they actually give us lots of leverage as you have seen in previous lectures。

😊，But the subtle point is whether coins are public or they're private。 What does it mean。

 So when coins are private， it means that Alice has has her own source of randomness and Bob has his own source of randomness and they just send messages based on this randomness that they own。

A more powerful model is public coins when actually。

 Alice and Boke have common sort of randomness that both of them see。

And this allows them potentially to agree on certain things without even communicating anything。

And for this result it will be important to allow not only public coins but to allow count many of them so what does it mean it means that not only we have like you know access to just like you know maybe some finite number of public coins。

 public random coins， but we assume that we have access to the whole sequence of random coins so basically they index by say positive integers or something like this and both Alice and Bo can use them to base the decision on them and why do we need count many coins because we want to operate with such things as Gausians or some other continuous random variables which require count many discrete coins to actually even produce a single sample right？

So。Countably many public coins is not the usual notion of communication protocol that is usually considered in the computer science literature。

 but because our upper bounds are in this model， we need to work with this model but again for the sake of this lecture it's not super important just like keep in mind that we have public coins and there are many of them so that's it。

😊，And since with our randomized protocols， we just require as always that success probability is at least two thirds。

 so basically if distance between two points is small then with probability two thirds。

 they say that the distance is small and vice vera。😊，Okay， so that's roughly the model。

 So let's see what we can do in this model。Of course， we can handle finite metrics， right。

 So for any finite metrics space， there is a protocol in this model it can even achieve。

 So basically I'm going to refer to this what me rewind a little bit。

 So I'm going to refer to this quantity as。😊，嗯。As like sketch size or like communication protocol size in this case and I'm going to refer to D as like approximation So if for finite metric space we can obtain any approximation more than one right just because the metric is finite。

 we can pretty much send the whole point right。😊，But what can we do besides finite metrics？

So the first thing is suppose we have suppose that ourometric space is just the dimensional Euclidean space。

 then what can we do？嗯。So okay， so Alice and Bob now have the dimensional vectors。

 each of the vectors consists of real numbers。Turns out that then the the following protocol words。

 again， you have seen it in previous lectures， but I'm just going to remind you a certain version of it that works in this precise model where we。

Like fix how many beats we would like to exchange rather than like so so we don't want to cheat saying that you know we exchange real numbers because each real number has like infinite number of information。

 infinite amount of information， so we will be identical and we will want to talk about like exchanging beats proper。

 right。Okay， so basically how can we design a good protocol for the Euclidean space so they need to sample G independent Gaussians using common randomness that they have public randomness and then they need to obtain basically fold the vectors using this Gaussians so obtain this numbers x tilde y tilde which is just dot product of this Gaussian vector with their product。

And now the intuition is that difference between x t and y t should give us a pretty good idea what the L to norm between x and y is。

😊，So specifically how we go about it is we basically。

 so we would like to estimate the difference between x t and y tilde。

 but it's also not very clear how to do because again these are real numbers。

 we don't want to send them， we want to do something with them， you know。

So the solution turns out is pretty simple， so we just take our real line on which these numbers。

I situated located and just basically randomly partition it into windows of size W where W is a certain parameter。

 And then we color each of the。Each of these windows in random plus -1。

 So all of that can be done using public randomness so we can sample where to start our random partition。

 This is random number between0 and w。And then we basically can use countably menu coins to basically assign this random plus minus one。

And yeah， so。呃。Then what what do we do we basically like Alice likeates x tilde on this line and bo likeates y tilde on this line。

 and then they obtain the respective plus minus-1 right。

 and then they basically exchange this plus minus- ones。

 and then they say that the vectors are close even on leave these plus minus ones are the same。

 So basically if both of them work plus one。Then they say it's close， if both of them got minus one。

 then they say it's close， if one of them got plus one， another got minus one。

 then they say that it's far。So let's analyze this protocol again， I'm going to be quite brief here。

 but let me just say that。The intuition is that basically if distance is closed。

 then probability that if you choose this window size carefully。

 then the probability that X t and y t end up in the same bucket is。Notevally higher。

Then for the case of far points， actually I have inequalities messed up here so they should be。诶。

I believe。The other way around。 So they should be like basically if the points are closed。

 then probability of collision is at least。Something。

 and if the points are far than the probability collision should be at most something。

And the point is， basically Epsilon one is noticeably higher than Epsilon2。

If we choose window size correctly。 So basically， Epsilon 1 minus epsilon 2 is omega of epsilon。

 right， So that， I mean， that's pretty like。That's intuitive clear right so basically if your vectors are short。

 then when you take a dot product of them with Gaussians then you will obtain Gaussian with basically slightly lower variance than in the farK and that's how you get this separation。

So basically the probability of our test saying close will be like nontrievally different in both of these cases and we can amplify it to again。

 sorry I have an equalities messed up here， this is just a matter of animation。

 but this probability of success can be amplified to two thirds using around one over Epson squared rep repetitions and just like doing majority voting。

嗯。So if you didn't understand what I'm talking about。

 let me just say that one line of it is we take this sketch using Gaussians and just discretize it using this trick of coloring line。

In random colors， and we need this disctization just to talk about， you know。

 sending beats rather than sending real numbers or sending integers or something。

But the punchline here is that for every epsilon legend and  zero。

 we can obtain approximation1 plus epsilon with sketch size1 over epsilon squared。

And we can do the same for LP distances where P is at most2。

 just instead of Gaussians you need to use P stable random variables。

 otherwise the protocol and analysis are exactly the same。

And the result you obtain is also exactly the same。

 so you obtain one plus Epson approximation with sketch size， one over epson square， protocol size。

 whatever。So okay， so now we get our result， we get to our result， so what's our result。Basically。

 if you have finite dimensional norm space。And for this finite dimensional norm space。

 there exists such a protocol， as I described， so basically like communication protocol with。

Exchanging S Bs and obtaining approximation D， so telling apart distances of most one versus mode than D。

 then there resistance embedding of this normal space， linear embedding。Inter L1 minus epsilon space。

And the distortion of this embedding is protocol size times protocol approximation divided by epsilon。

So what what what what the hell is this L1 minus epsilon and why do we care about such a result？

 So L1 L1 minus epsilon， So this is like Lp space for P smaller than one。

 It's not even an normal space。 It's not even an a metric space because it doesn't satisfy tri inequality。

 But nevertheless， this space is still useful because actually for this space。

 you have good sketches。 So again，This table random variables exist even for a piece smaller than one。

 So basically for L1 minus eppson， you can get good sketch with。😊，Very good approximation。

 So basically， this result gives the characterization。 So norm allows a good。😊。

Communication protocol for the sketching problem for business estimation problem， even don't leave。😊。

It embeds into like particular space that is easy to sketch。 So basically， in some sense。

 this is a complete problem in this sketching。 So to say， by the way， any questions about the result。

 do you even follow me， do you。And so the， the， the SDD protocol is the thing you described at the start。

 it was deciding like。The distance is bigger。Yeah， so what are the questions， sorry？I guess。Okay。

 so wait minute。Yeah， yeah。Okay。呃。Okay， so let me give a few comments about this result。

 first of all， it's formulated for norm spaces， but you may hope for this result to hold for general metrics。

 not only for norms， so it turns out that this is false for general metrics。

Also like certain examples demonstrate that this SD bound is tied so you cannot improve so for example。

 you cannot prove bound like square root of SD。 So basically you really need this S timesD。

But what is not clear and what's an open problem， though likely it's a hard problem because it's equivalent to certain known hard problems in mathematics。

 but a priori might like it still might be true that actually this theorum holds with a1 minuscephone replaced with a1。

😊，诶。For this L1 case， we can actually also obtain certain result。

 but then the distortion that you obtain for embedding Intel1。

 it would depend on the dimension of your normal space。

 So it would be something like SD times log of the dimension of your normal space。

Whether you can obtain dimension independent bound like this， that's an open problem。

 so I don't know what the answer is。嗯。Okay， so。Like， why do we care about something like this。

 because it allows us to show lower bounds for communication protocols of our sketches？So basically。

 so I showed you that if communication protocol exists。😊。

You can obtain a certain nice embedding into a efficiently nice space。

So if you take this result in the contra positiveitive， then you will get that。

If em Beijingj doesn't exist， then there is no communication protocol and this is a very nice implication because nonabilityability results。

 they are much easier to prove than communication lower bounds because in。

 intuitively speaking because embeddings are much more regular objects。😊。

Linear embedding specifically。So we obtain certain new lower bounds。 again。

 I'm not going to talk too much about them， but basically。Both of them are still state of the art。

Sorry again， like this slide is wrong so they should be communication lower bonds from embedding lower bonds。

 not sing lower bonds Okay but this is so the lower bonds for communication we are getting for spectral norm so spectral sorry not spectral norm my bed shutt in one norm or trace norm。

 which is basically just some of absolute values of eigenvalue of say asymmetric matrix。

And then the second norm for which we obtain a new lower bound is Earth more distance。

 so again intuitively this is just like if you are on the plane you can consider sets of like n blue versus n red points and then the distance between this sets is defined as minimum cost perfect matching where underlying cost is just Euclidean distance on the plane and then it can be turned into enormous space if you allow like weighted sets or whatever。

 not super important。But then for this normal space。

 we actually obtain first non communication lower bound for hour。

Distance estimation problem sorry El， just to make sure I'm not misunderstanding did you mean embedding lower bounds from sketching lower bands or did you mean yeah yeah yeah。

 I mean scaping lower bounds from embedding so they sketching bands from embedding bands Okay so basically we take existing non inbedability results and just use our Ethereum and more or less a black box way and just obtain communication lower bounds because if they would be a good protocol then they would be good embedding but embedding doesn't exist by nonthereemum。

So yeah， that's the primary application， but also I think this is just like。

 you know philosophically reasonably interesting that the only way to obtain good communication protocols for distance estimation problem for normal spaces is to just embed them into L1 minus epsilon or L1 and use P stable random variables。

 So basically this like。😊，Sketching using stable random variables in some sense。

 it's the universal way of sketching distances if your magic space is a normal space。

 I think it's pretty interesting。Okay， so let me talk about the proof。

 so basically the proof consists of two big parts I'm going to give you almost the full proof like if time permits of one of these parts。

 but not the other one。😊，So。Basically， the starting point is we start with this SD protocol。

 as I defined in the beginning。And then we obtain certain emdding。

 but not what we actually want in the end。This will be much weaker object。

So what is this object so basically it's an embedding of our space into a Hilbert space Hilbert space is roughly speaking like infinite dimensional analog of L2 so let's for the sake of this lecture abusing notation let's just think about L2 it's not quite L2 but it's kind of like infinite dimensional L2。

😊，So basically we obtain map from our norm space in2， it doesn't have to be linear。

 but what we do require is that for every two points。

 basically short distances get mapped into short distances and large distances get mapped into large distances。

 So basically distances at most one。Turn into distances at most one and distances at least 100 times SDD turn into distances at least 10 in the image。

So this is much quicker than we won because this just works for a single distance scale and because this is not a linear em bedding。

 it doesn't have to work for other distance scales。

But then we use geometry or some like genetic and analy arguments and obtain what we want。

 So then we kind of like。Youulize this mapping and make it nice and linear and turn it into actual linear embedding intel 1 minus epsilon with distortion。

 so all distances get distorted by a factor at most SD the over epsilon。

So basically I'm going to show you as much as I can from the second step so basically how do we turn this weak embedding into strong embedding and I will barely mention anything from the proof I'll tell you what ingredients do we use for the first part and in some sense it might be more interesting for computer science like basically for people with computer science background but unfortunately in order to present the full proof of this first part I need to introduce a bunch of hammers that we don't have time for basically including some how to show communication lower bounds using information theory of this like direct direct sum theorems and stuff like that but I will mention some of these things in the on the next few slides but then I will turn to giving you the almost。

Like at least good chunk of the proof of the second part。

 how to turn a weak bedding to the stronger bedding。

Could you quickly remind us what a linear embedding is what makes a right It's just a linear map。

 So basically like if you have mapping between normal spaces。

 it can it may or may not be linear right So like basically linear map as a map between linear spaces vector spaces。

So basically it's just like you know， f of x plus1 f of x1 plus x2 equals to f of x1 plus f of x2。

 kind of like if all your spaces are finite dimensional， then it's just you know。

 like multiplying vector by matrix， that's what linear embedding is。Okay， does make sense， yep。

 thanks。嗯。Okay， so let's talk before we dive into the proof of this geometric part。

 let's talk a little bit about information thetic part。

So that's our goal so our goal just like I'm reminding you of the previous slide so our goal is to cook a map that mobs distances at most one and the distances at most one and distances that are large into sufficiently large distances。

😊，And let me tell you what is much easier to obtain。 It turns out that it's much easier。

 It's still not entirely trivial， but it's much easier to obtain almost what we want， but not quite。

 So basically， we can obtain the map into L2。😊，That map distances。

 so the first condition is the same distances at most one get mapped into distances at most one。

 and distances at least D get mapped into distances that are slightly more than1。

1 plus2 minus S two to the power minus S。Right if we have protocol with communication size S and approximation D。

 and moreover， this weakest statement is true not only for norms。

 it's true for general metrics and it was used before our work by other people。

 but unfortunately it's not good enough for us， we can't just use this easy statement。😊。

And then upgrade this weekend bedding into stronger bedding。

 So we basically the crucial thing that we need is we need a large gap between so basically we need this gap between one and 10。

 So basically it should be at least large constant。 I think it should be at least8。

And here we have the gap is just like slightly more than one， and it's exponentially small in the。

Communication size。So basically， that's why this easy statement is not enough and we need to actually obtain one ver of1 on the right hand in the image。

That's why we need to work much harder。And again， we will have a proof by contradiction so basically we want to say if there is a protocol communication protocol for the distance estimation problem。

 then there is such and such map and basically we will be showing that I assume that there is no map right so then I would like to show communication lower bound that will be our way of proving it。

😊，So how do we show this？So we show that suppose that there is no such weak mo that mops small distances into small distances and large distances into large distances So just to make sure I'm understanding。

 so are you now provingrov the ak results with exponential difference or you proving the no' I'm not now I'm giving you outline of our proof actually like I think this ak result iss it's basically quite simple。

 So let me maybe say a couple of words So the idea of for this easiest statement is just do round delimination in your communication protocol and reduce it to just one round and probability of success of this would be something like one half plus2 to minus S something like this。

And then basically then one round protocol， you can turn to such embedding by just like spelling out all your probability space of like random coins and kind of like telling what message is being sent again I'm like being extremely hand wave but you can actually like the other player just basically guesses the message that was being sent message is one beat so basically editing just becomes like whether whether the beat was zero it's like easy to think about as embedding in the he space So so what was S again sorry then S is communication size So it's like number of rounds or you can assume it's like number of beats sent。

 but you can also assume that it's like S rounds right or two s or something like this So you basically eliminate all these rounds except one So basically they just exchange one beat and then whatever type bit they exchange。

 you can just get an embedding out of it pretty easily。

So that's what this aK and Andia crowd gamer paper does it's like Lema1 in this paper of course basically then they do much more work for the mainers this is just。

Terial statement that they show there。 Okay， so but how do we how do we how do we obtain a stronger statement like what we need。

 So if we， if we know that there is no good in。But basically the fact that there is a good embedding you can encode as a certain convex program right so basically you just know that for every close points。

 your points in the image should be closed right and for far points they should be far so this is certain semideite program and we can take dual and basically obtain what's the condition which is equivalent to the absence of this weak embedding。

Tns out that this is the following statement and again， there is a little bit of subtlety here。

 you cannot just use like。Dualality directlyrely because this is not even a finite HDP it can be infinite and for infinite convict programs dualality holds only with some caveats it's not literally always true but we can kind of like make it finite kind of up to some approximation whatever it's not super important let me just say what we obtain So what we obtain is。

😊，Basically， we obtain two financially supported measures， mu close and MuF。

 such that close measure is supported on pairs of points at distance one。

And far measure is supported on far pair of points。

 so at distance like 10 SDD 100 SDD or whatever it was from the condition of weak bedding。

And then for every map from our space in a unit ball of Alto。Basically。

 we have the following inequality。 So basically with respect to close measure， squared difference is。

Not much smaller than a square difference with the spectral fire measure。Minus some select。

And so this is certificate of non imbiability， basically。

Implication in the opposite direction is easy to see， so basically if you have such two measures。😊。

Then you can easily conclude that there is no weak bedding because like if there would be weak being。

 then you can take this embedding as F。kind of。And it would refute this inequality。

But so so like we show that like basically the interesting part is this direction that is on this slide。

So we obtained this two hard measures， close measure and far measure with respect to which we have such inequality。

 and then how do we get this to communication lower bound， how do we show communication lower bound？

First of all， we will show it for the wrong space， not for the space act we want。

 but for certain auxiliary space， and they will introduce this space now。Actually。

 interestingly enough， this implication was shown before by Andtonia Jman Perashko。

So they showed that such a pair of hard measures。Implies communication lower bound for this auxiliary space。

 So what is this auxiliary space。 So this auxiliary space is。呃。Basically， in this space。

So it's like case power of our original space with like infinity in it。 So what does it mean。

 It means that in the new space。The points are two poles of size K。

Of the points from original space X， right， And how do we measure distance between two such twoples is we take distance between first components distance between second components。

 distance between case components， and then we take maximum， absolute like maximum distance。

 That's why it's Lfinity。 So you can define in similar way LP product。And so on and so forth， right。

 but for us， we will be defining afinity product。And then so basically。

 Ania Jeremy Peraarch who show that if you have such a bun inequality。

 like I showed you on the previous slide， then your infinity K fold infinity product of X requires。

Linear and K communication for distance estimation for approximation， roughly SD。

And let me give you a little bit of context， just historical context。

 so basically this result is a generalization of disjointness lower bound from this paper by Barius F Jra Kumar and Siva Kumar so basically this paper BjKS it kind of like introduced and developed the tool of information complexity of proving communication complexity to lower bounds and it provided a particularly nice and very conceptual and clean proof of that you know like there is this standard disjointness problem that Alices has。

😊，A set subset of some universe， book has a subset of some universe。

 and they would like to check if this sets intersect or not。

And fairly intuitive statement that actually there is no better protocol than the naive one。

 naive one is just like to send the set more or less。And even for randomized protocols。

 you cannot do better much by more than a constant factor。

 and this was known how to prove before this BJKS paper。

 but the proof like they provide it's very clean， very conceptual and also it turns out that it generalizes too many other problems so basically this antonia Jm petrarch implication that this pair of hard measures implies communication lower bound for kfold infinity product effects。

 it is directact generalization of this barrier of JM co co information complexity framework。

I'm not going to talk about it much， but like I really recommend you reading this BJKS paper。

 it's like really really beautiful and very instructive and if you want to work in the communication complexity area or like if you want to prove lower bounds for streaming。

 I highly， highly， highly highly recommend this paper and thisJP reference。

 it's kind of like cute generalization of it that turns out to be exactly what we want。😊，嗯。

Just little so I can remind all the students， you know we did talk about BJKs in this class。

 we didn't cover any of the proofs in it， but we used it as a black box namely the fact that。

There is this communication lower bound for multiparty set disjotness。

 we used it to prove lower bounds for LP norm estimation for large P or LP heavy hitters for large P。

Yeah， okay， that's the same paper El is talking about yes， it's the same paper。

 but I'm referring to a different dis jointint lower bond the the lower bound I'm referring to is just for two parties。

呃。But unlike the one that is July talking about where like， you know， in for the multipart。

 it is joint as it's like first party sends to the second party， the second to the third。

 third to the fourth and so on。Here we allow unrestricted protocol so basically two parties can exchange any bits in any way they want。

so it's it's kind of like two incomparable results， let me just say。

 and this paper has like a few more results， it's like very， very nice。😊，嗯。

Okay and so we showed lower bound for the wrong space but what can we say about our original space so this is a kind of cute tick again maybe let me not show it to you now because I want to spend quite a bit of time on the second part of the proof on the geometric proof how to how to obtain strong embedding from weak embedding but let me just say that there is a simple ti that shows that actually such a lower bound that I have in the red frame here。

So this one。It implies also lower bound for。For distance estimation in the x itself with communication S and approximation D。

 and roughly speaking the intuition is the following again。

 it's approved by contradiction yet another time， suppose there would be a good protocol for x。😊。

Then turns out that I can obtain a sufficiently good protocol for this K folder infinity of X。😊。

And basically the reduction is the following， so there is a naive way of obtaining an infinity K of X。

😊，Nive protocol is just like let's use the protocol for x， but we will use it k times， right？

And that's not what we want。 So here， in order for this implication to go through， we need to。

We may not lose in communication size， but it's okay to lose an approximation。

So basically we can't afford to run k copies of the protocol for x。

 but the trick here is instead of running k copies of the protocol for x。

 we will just run a single copy， but instead of running it on like original vectors from X we will run it on like folded vectors with random signs again for the details you can look at how paper but like if you think about it a little bit like I'm sure almost all of you will in it pretty quickly it's like a fairly cute but simple reduction。

😊，Okay， so now let me okay， so now let me be more detailed。

 so I would like now to talk about genetic part of the proof and actually I'm going I'll turn from slides to actually writing things so that you know。

It would be easier for you to follow。嗯。Let me make switch now。so。

Let let me remind you what are we proving， so what I want to prove for you now is the following theorem。

So basically， thetheum says the following。Suppose you have a map from your space。

Inter Hilbert space or whatever L2。I assume it's kind of a tool。 It doesn't have to be linear。

And the mapp mapps distances at most one in the distances at most one。And distances， at least。

Hundred SD。It mapps inter distances， at least 10。So that's what I have so that's what we obtain from the information thetic part So basically remember we showed that if such a map doesn't exist。

 then there is a communication lower bound， but because we have communication upper bound。

 then it means that this map exists。😊，So what do we obtain then？

My goal is that existence of such F implies。There exists linear embedding。Now it's linear。

 So let me call it。 I don't know G， maybe。From x into L1 minus epsilon space。

For every epsilon and the distortion。SD over Epsilon。

So that's our goal of the remainder of the lecture。And okay， so essentially there are two big parts。

Like I'll make this。 So basically intuitively， we take a map that kind of like。

Nice on a single distance scale so it kind of preserves a single distance scale。

 and then we obtain a linear embedding with distortion that like because it's linear。😊。

And it has bound a distortion that preserves all distance scales at the same time。But in some sense。

 we give up a little bit because original map was in2 and the final map isn int a slightly less nice nice space。

 It's like L1 minus Epsil。Okay， so how do we do this， so we do this into two steps。

So can I ask you one more question Sure you mentioned that you could get this log of dimension in there for L1。

 is that is that just by setting Epsilon to be one over log dimension and using holding Yeah。

 yeah yeah， pretty much。 So basically we say that you can set up some to be sufficiently small and also we we use dimension reduction until L1 minus epsilon。

For such spaces。Yeah， so we have linear embadding into L1 minus epsil。

 So by dimensional reduction results， we can assume that L1 minus epsilon is not too high dimensional。

 It's like poorly。Poly dimension of x dimensional。 And then it means that it's sufficiently close to L1。

 and then we optimize over epsilon and get this log dimension of x exactly。Yeah。

 like what you're saying or you said polyx dimensional or polydm X dimensional Yeah polyd maxax yeah actually in fact it's like the stronger result called it's like so basically if D is the dimension of x。

 then you can do dimensional reduction to D polylog D for a1 minus epsilon。

 but for us it would be okay to have just polyd。Okay， so yes， this is， this is correct。

 So basically this result for about L1 minus Epsilon implies result L1。 So okay。

 so let's let's show this。And basically this consists of two big limas。

 so the first limma it makes the mapp somewhat nicer。

And then the second Lema makes it even nicer and turns it entirely linear you em bedding。

 So let's declare our intermediate goal。 So intermediate goal is。😊，Obtain basically F tilder。

A map from X to a Hilbert space， by the way， I'm gonna like I'm gonna write H for a Hilbert space。

 even though it could be different Hilbert spaces every time。

 let let me just like abuse the notation and not write everywhere like H H prime H2 prime H till H2 till the like every every single time I write H it could be different Hilbert space。

😊，Roughly speaking， it's always all to just like potentially of like different crinity of dimension。

 It's not gonna be too important for us。 basically， like for us。

 just Hilbert space is a space where we can take dot products and yeah。😊，They behave as you expect。

So， so what like， what does this Ft the satisfy。 So the first condition is that。F tilder of。

X1 minus f tilde of x2。It's at most。2， tower1。X 1 minus x2 square root。

And second condition is e distance between x1 and x2 is efficiently large。More than。嗯。

So let me call this1 as D some other letter， let me call it Delta。

 just not to write this1 as D everywhere。So basically。

 like this detta is a threshold for large distances。So then if my distance is at least delta plus2。

 then distance in the image。Is， at least。Tautu， square root。minus square root of8 to1。

So basically what did change compared to previous compared to initial map。

 basically now the second condition is kind of the same。

 so basically large distances get moped into large distances， nothing much changed。

But the first condition became nicer， not only we know that small distances get into small distances。

 we also have that also now can extract some useful information about large distances， you know。

 basically large distances don't blow up too much and small distances stay small。

So we kind of regularize it a little bit。So that's our I first goal。

 And now you can also see why I required Ta Oh sorry， let me also， what am I writing。

 So let me also call this thing Taowa and Tao2。嗯。So that's why I require Tau2 to be like at least eight times tau1 in order for the second condition not to be V。

And that's exactly why we need this efficiently big gap between Tau2 and Tau1。Otherwise。

 this step just becomes v and we can get anything from it。So let me show the proof to you。

 it's actually kind of not very difficult but kind of cute and requires a few tools that I think you need to know about and then I'm not sure if I will have time to show how to upgrade this map and linear embedding but at least I will try to outline the sketch of the results like like in the best case I will show you most of the proof in the worst case just like you know main steps。

😊，Okay， but let's let's see how to like obtain this intermediate goal So basically intermediate like this result is just a composition of two other results。

嗯。So like， let me let me give you these two facts。 So the first fact is。嗯。

Square root of Euclidean space。And beds back into Euclidean space。

So what what does it even mean like what the hellam I writing。

 So basically if you have Uuclidean metric or if you have like some subset of Hubert space。呃。In fact。

 if you have any metric space and you take square roots of it。

 so basically if you consider the same set， but all distances you take square roots of。

 it will still be a metric， it will still satisfy triangle inequality just because you know square root is a concave function。

😊，So its still a tri inality， but we need additional stronger statement that if initial metric was Euclidean。

 then square root of it is also Euclidean， so it can be embedded back into Euclidean space with distortion one so you don't lose anything in the distances。

😊，And this is not a trivial fact that actually is one of these results published by Schenberg in 30s。

 The proof is not very difficult， but it kind of like relies on this theory of positive semideite functions。

 which by the way we will see later in this lecture and it's actually like pretty subtle so it's not like obvious the statement might look obvious but actually a statement is also not obvious if you think about it even you take even if your original metric is not just like high dimensional Euclidean space but just a real line and basically now you define a new metric on the real line which is like square root of original metric the fact that this embed in the Euclidean space that's also nontrial and actually like general result follows from this one dimensional result pretty easily。

😊，But long mentional result is three key El， so I have a question about this。

 so you mentioned if I take square roots， I still have a metric or oh， I still have a metric。

 but not necessarily a norm space。That's right。 Yeah， Okay。

 because like C times X will not have the norm。 C times the norm X。 Yes。 Yes， yes， yes， yes， So。

 in fact， this embedding is not linear to the one that I'm just mentioning precisely for the reason that you said。

So if you take like square roots of Euclan space。Then yes， you can embeize a into euclidean space。

 but it can't be a linear mo because otherwise it would break homogeneity。Does make sense。Yeah。

 sorry， yeah， thanks。Yeah， so this is the first fact and second fact that we need is so this is fact one。

 this is fact two。😊，Basically， we will use certain extension theorem。

 so what is extension theoremums？so诶。Okay， so the classic result， which we will not need。

 but what we will need is a certain variation of it。 So classic result is a theorem of Ki Brown。

So Ki Brown Theorem says the following。 if you have Euclidean space， so this is Euclidean space。

And you have any set in it， it can be finite， it can be infinite， it can be measurable anything。

 literally， it can be any set whatsoever。And suppose that you mo this certain to another Euclidean space。

And this map is one leapes。So what is one lipitz that means that distances do not increase。

 distances can only decrease between points under such map， so this is one lipletitz。

So then Ki Brown theorem says that you can actually extend this map to the whole space。

 so now you can actually like if you have new point in this space that is not one of the original ones。

 I can define this map in a consistent way such that the resulting extension is one lit as well。

And it feels like， you know， it feels like kind of useless result like because of course we have lots of room right。

 we can define this we can define this function on red points in whatever way we want。

 how come this is， first of all， non trivialvial and why this is useful none of these questions is easy but it's actually like it's not a difficult theem but it's kind of cute and the tol uses duality in some nice way convex duality。

😊，Why this is useful， we will see later in the lecture。

 like we will see very soon in fact that certain variant of this extension theorem is useful。

 but let me just say that there are many known extension theorems and two of them that then I will have mentioned one of them is scattered brown another I'm about to mention now。

 this is just know scratching the surface that there is like wholesale up field of geometry which is concerned with like extension theorems。

😊，So the specific extension theorem what we'll need is the following。

 so suppose that instead of Euclidean space original space is general matrix space right so now instead of Euclidean we have general x。

😊，And your map is still defined in the Euclidean space。So can I obtain the same result。

 So can I generalize its brown theorem， But when domain is general metric instead of equilibrium gradient space。

 turns out that you cannot not。 And the are known counter examples。

 I think it even false when X is just a one distance。

But what you can show instead is extension theum where instead of one litts mops。

 we can see there one half elderer mops。So let me explain what this means。

So basically1 half Hol condition， so we say that this capital F is1 half ho is if F of x minus1。

Minus F of x。F of x2。So norm is at most some absolute constant times square root of x1 minus x2。

So this is a weaker condition than lip fitnessness。And basically， like。

These are incompar theorem because we assume less about our function that it's one half here。

But then we make it work in greater generality that you know like。

Instead of Euclian domain you can have any metric space whatsoever that you want and in fact proof of this theorem is not very different from Ki Brown's theorem but also like duality in our paper we have like reference to a classic book where you can actually write where we can actually find nice proofs of both of these theorems and way more so these are the two classic facts that we need。

😊，So basically a square root of Euclidean space can be also realized as a Euclidean space。

 and we need this variant of K brown theorum that says that any one half holder mop defined on the general metric space into Euclidean space can be extended to the whole space。

Originally it's defined only a subset， sorry， and subset can be anything。So okay。

 so let's prove our E theum， Let me remind you what the theum was。

It's actually not ethereum of this intermediate goal。 So basically。

 I would like to construct the function from。From my space into。

Hilbert space that long distances maps into led distances and maps into large distances。

 and basically it is also one half holder。On the upper bound side。So okay， I mean。

 you see this this like one half in the exponent that's not a incidence。

 that's exactly why actually we need both of these statements。😊，So the proof is the following。

 so we take our original map F。😊，So F is our like weak bi。

And then let's prove the following very simple observation， so claim。

So basically our week in Beijing it mapps short distances into short distances it distances at most one and the distances at most tau 1。

 right， So basically this allows us to derive a corollary that for every x1 index2。

So basically for like basically intuition here is that on large distances。

 F behaves lips in a lipsuttz way， namely。F of x1。Mus F of x2。Is it most。Maximum of。Wd two types。

 x 1，- x，2。Time star1。Okay， so let's first of all， part what the hell did they write？

What the color just wrote。 So if distance between x 1 and x 2 is tiny。

 then this statement just says that， you know， like。If distance between x1 and x2 is very small。

 then the distance between F of x1 and f of x2 is at most tau 1， right？That we know already。

 because this is just part of definition of a weak in being。

 But this statement becomes interesting when distance between x1 and x 2 is large。

 So if distance is large before we didn't know anything on the upper bound side。

 And now we know that， you know， it's like kind of les with constant two times tau 1。 And by the way。

 why this is true， it's very simple。 So basically， if you just take any points that is efficiently for x1 and x 2。

😊，You take the segment between them。And then you split it into equal part of size1。Right。

Up to a rounding error and then you just apply the fact that distances at most one get mapped in the distances at most down one。

 and then we just use triangle inequality， right？Why we lose this factor of two here is precisely of this rounding error。

 so what if distance between x1 and x2 is just like a little bit more than one。

 but then we have to have like two segments， right？😊，So。Yeah， so that's the whole proof of the claim。

And now。Let's just。Apply our first fact。 So let's just use the fact that。

Square root of eucl space can be mapped into the eucl space。嗯。So it means that we can get a new map。

 which we call F tilde， sorry。呃，FTU的。That is from X into Hilbert space。30 the app。嗯。Yes。

 so basically now we， so basically， we can take square roots of Euclidean space and realize that as Euclidean space。

 So we can take this。A largeatch scale lipid condition that is written here。

And say that for the new map， it holds with square roots， or namely。嗯。F of x 1 minus f of x 2。

Is at most maximum。 So if till till a maximum of one。 then we have two times。

Normal x1 minus x2 square root。Times。Square root01。

And then the second condition for now we just take from the definition of a weak in bedding。

 we say that if distance。Between x1 and x2 is at least D。

Then the distance between images is at least square root of total。

So for now I just used this claim and the fact that I can compose this map with a map that embed square root of my Hilbert space back into another Hilbert space。

Okay， so now it's time to use my extension theorem。So， so what do we want？ So we。

Like why we are not done yet。 So second condition is kind of what we want。

 So large distances get up into large distances， but we know nothing for small distances。

 So if if distance between x1 and x2 is very small。I'm sorry， I should have read Ti this here。

If distance between x1 and x2 is very small， then the first condition gives us nothing。

 but we want to obtain some folder condition that we later want to use。So for this。

 we need an extension and the extension theorem actually we use in a very simple way。

 so we take our space X and we find a net in it。😊，So this is one net。

 so any point is within distance 1 from n and at the same time points in n is R1 separated。

So you can construct such a net using grid algorithm。 So here we need to be careful because we like。

 you know， our net can be。Like infinite， but it can still be done。At least intuitive should be clear。

 So now we take our map of Tilde and just consider its restriction on the net end， right？

So the nice thing about this restriction is that now it's one half shoulder。

And this follows from our claim one， so basically it follows from actually it follows from this first condition。

Because if points from the net are different and the net is once separated。

 then actually maximum will never be one and maximum will always be the second term。

So it's one half holder with constant square root。Sorry。Square root， two times star one。Sorry。

 did you define N on the previous slide， just a warning that I've never used that word yet in this class？

Oh， yeah。 So， okay， so let me say what this means。 So we choose a subset of our space such that。

So it's basically just like notion of Epsilon net， basically any point from our space is within Epsilon in this case Epsilon equals one within distance one from some net point。

 so basically balls centered in points of n of Radius1， they cover the whole space。

And at the same time， the second condition that we want is that distances between any two points in the net。

 they are more than one。And you can always construct such a thing。For any metric space。For example。

 if your space is finite， then you can just， you know， like if some point is not covered。

 just take it as a center of the new bowl。removed the ball and recourse。For infinite case。

 you need to be slightlyy more careful， but it can be done as well。

 So you kind of do it for larger and larger bowl。 you know when it works。

So the point is because the net is once separated， our F tilda function that we defined on the previous page。

 restricted on this net， it's one half holder with a constant square root of 2 tau1。So。Now。

 we have this one half color like one half color function。 We can use our extension theum。

 so we extend， extend。This F tilder。To a function G defined on the whole x。

And what conditions do we know。 So restricted on the net， it coincidesides with F tilder。

 restricted on the net。And second， this G is one half holder。With constant square root2 tower1。

And the second condition is a big victory for us。 Why is that， So this is great。

 Because that's exactly what we wanted。 So remember， that was our intermediate goal。😊。

And this is exactly the first con of this intermediate goal。

So now it is enough to check that we have also the second condition。

 So basically so now because we so we took a function that maps large distances into large distances。

 But then we kind of like， you know， lost all the information about the function except values in the net。

 And then we use the extension theorum。 So why do we still have that large distances get mapped into large distances。

 That's not very hard to see。 So basically intuition is that if you have two faraway distance faraway points。

 then you can find net points。That are like within distance one from these two points。

Then on these net points， function stayed the same。

 so we have the condition that basically distance between images of net points is still large。

But then we use， also that。The function is one half holder。

 so we have that basically these distances did not blow up too much。So I'm not going to write this。

 but this gives us exactly what we need in the end。So， it gives us。Basically， this condition。

So precisely， we lose this plus two。Because because of this net argument， net rounding argument。

 and we'll lose this here a little bit also like precisely because of this triangle inequality。Okay。

 does make sense。So our intermediate goal will prove give or take。Okay。

 so now let me in the remaining 24 minutes， let me tell you as much as I can about how we take this new function of Tilde。

And upgraded into linear embedding into L1 minus epsilon。

So it still feels you know we're not quite done right so first of all this embedding is not linear and second。

 pure our upper bound became somewhat nicer， but lower bound is still just for a single distance scale so like how do we deal with it？

😊，Okay， and here we will use the power of free analysis。Here is how。

So let me formulate a statement that we are approving this is again just like slightly different just。

Simplifying the notation a little bit， but basically the statement that we need to prove is the following theorem。

Suppose that you have a function from X in the Hilberts space。And suppose that F of x1。

 F of x1 minus F of x2。Is it most absolute constant time square root of x 1 minus- x2。And if。

X1 minus x2 is large。Then distance between x 1 and x 2 images of X 1 and x 2 is also large。

 say at least one。Then I would like to prove that there exists a linear embedding。

From x into L1 minus Epsilon， with distortion。嗯。Something like dealt over epsilon。

So that's my goal for the remainder of the lecture。 and this would conclude the proof of our theem。

So okay， so here is what we need to do here。So嗯。Again， we need a few facts。

Let me introduce them as as we go。 So the first fact is that。嗯。If you have a Hilbert space。

You can always map it into another Hilbert space with the following properties。Basically。

 dot product between images of this embedding。Is exactly equal to e to minus squared distance between。

Butty images。So this again uses the three of semiite sorry， positive definite functions。嗯。So。Again。

 this is like classic result of Schronberg and again， this is not easy。

 and the map is like very nontri to construct。Actually。

 like one one way to one thing to notice here is that this is not just a map in the Hubert space。

 It's， in fact， a map on a unit sphere of of your space。 And why is that Because， you know。

 if if H1 equals to H2， then the product is equal to one， right？

 So it means that length of every vector in the image is exactly equal to one。 So we do map。Onto air。

 well， not onto， but。Wem up to unit sphere in age prime。

So let's take this Mb G and compose it with Mp F。😡，So let's define a new map of Tilde。

 which is just composition of G and F。 So what do we know about this map？

So let me write the conditions here。Oh in this fact， F1。

 I feel is that something that people use a lot in machine learning。 Yeah， I mean。

 as you will see what I'm gonna talk about now， it has to do a lot with all these kernels and stuff like that。

 So yes。In particular， I think。Okay， let me not say anything on the record。Yes， of course， of course。

呃。O呃。So so what do we know about this composition So basically it's just the same conditions as before。

 but now instead of distances we have dot products right just because we you know like we turn distances into dot products by using this map view。

😊，Yes， this is like feature representation of whatever Gaussian kernel or something， right。

 Is that what you're referring to。Yeah， I think so I forgot the name， but yeah， yeah， yeah， Okay。

 Okay， good radial kernels or something。 Yeah， Okay， good。 So so what do we know we know。

 we know here that， you know like do product between。F tilde of x1， F tilde of x2。

Is at least e to minus k。X 1， minus x2。So we had square root， but because we have square。

 now we have first power。And if distance is at least delta。Then， the product。Is at most。1 hour E。

So this is just real。 Nothing much is happening。 So now we are going to use the fact that， you know。

 like， we will use characterization of thatt products。 So basically， if you have。

So basically if you have any set with pairwise values on it， so like kernel。

 so kernel can be realized as a dot product in some Hilbert space if I don't leave this it's like symmetric positive definite kernel。

So what does it mean， it means that， you know， we have a function K， like x1 x2。

And it's like non negative symmetric。And positive D it just means that if you take any endpoint。

In your space。And form a matrix K of Xxg。This matrix is PhD。And this is if and only leave， in fact。

So in one direction， it's obvious if you have dot product， clearly。

 it has this property in the opposite direction， it's like also true。

 you just need to work a little bit。 also like one of the classic Schumberg results， basically。

 it's like。Really like sponsored by Schaonburg this part of the talk。II mean， is that the same。

 is that the same thing as the spectral theorem or is I'm not sure。

 I'm not sure it's the same spectral theorem， I think says a little bit more。 This is。

 but I'm not sure。 so let's not let's not let's not argue about it。 We don't have too much time。

 but it's it's not a hard resultle。嗯。So okay， so now there is a one step that whose proof I will not show you and both because it's not very like enlightening proof and because it's like not very interesting part of the proof。

So the second step is to actually say that。So okay。

 so basically previous conditions from the previous slide。

 previous page tell us that there exists a kernel that satisfies certain properties， right？

Just because this embedding Fda gives us。Some condition on the top products。

So next step is to say that actually， without loss of generality。

 we could have taken this kernel to be shifting variant。 So basically。

 we can assume that our kernel x1 x2 satifies。😊，That it's like phi of x 1 minus x2。

So then what does it mean in terms of conditions on the file， what do we have？呃。

So we have that like5 of0 equals to one。So Phi is a function from our space into real numbers。嗯。

Fie of eggs for any eggs， is at least。E to minus k。Time is normal x， and if。

So this is second condition and the third condition if normal x is at least delta。

Then firefax is at most one over E。Why can we always do that， we need to do certain symitization。

 we need to take our kernel and apply certain averaging procedure to obtain and shift andvari version of it。

But the annoying thing here is that we do averaging over some like。Not。

 not some obvious distribution because there is no obvious distribution on X， right。

 but we need to do some kind like basically this averaging requires some Xome of choice。

 and it's certain crazy objects that we need to use for averaging。 It's called like so so called。嗯。

Bound a shiftingvari mean or something like this。 and it requires that of choice to build。

But it can be done。So we do obtain this positive definite。

 Now it's called positive definite function because it's like。Positive definite kernel。

 but like shift and variant。 and this positive definite function has these properties in0， it's one。

😊，Close to 0。 it's not too far from one。 So in particular， it's continuous and 0。

And sufficiently far from 0， it decays non2 value。 So basically， like if you step away deelta from 0。

 then your function is always smaller than one over epsilon。 sorry，1 over E。

 So it's smaller than some constant， whatever。So now we can use what's called Bochners theorem。

So what is the Boner theorum？Bovner's theorem is a classic fact。

 actually not very hard also to prove。嗯。That says that。

Like it exactly characterizes set of all possible Fourier transforms of random variables。

 So if I have random variable on the dimensional space。😊，I can consider its Fourier transform。

 I will say in a second what it is， and then it turns out that by Boner's theorum set of such Fourier transforms are exactly。

😊，Positive definite functions that are equal to one in zero and that continuous in zero。

And this is exactly what we have here， so by Boner's theorem we obtained that there exists distribution mu。

😊，Over。Let me write it this way。 Let me write it like。R。To the power dimension of X。 I want， I。

 I could have written X， but it， it would be a little bit misleading to write that it's defined on X。

 It's defined in some sense on the dual space。 But let's not worry about it。 Let's just say it's。

D dimensional space where D is dimensionality of our regional norm space。

So there exists a probability distribution over this space。

 such that it's Fourier transform with fee， but what does it mean that means that。For every。

V for every x。Expectation over。Some additional vector sample， according to this measure is。

Of of this fullyharononic。Is exactly equal to phi of x。

So we kind of take in transform and obtain certain。Probability distribution。So okay。

 so now the like we are very close to be done， at least in terms of stating what I'm embedding is let me maybe state what the' embedding is。

 I don't think I will have much time actually to prove the quality of it。

 But let me just give you the intuition。 So the intuition is that this distribution meal turns out that it is a decent。

Linear cage of x。So what do I mean by that， So let me actually state a certain lemma。

On the quality of this of these distribution。 So like， which properties do we want。

 So we have that for every x in x。Basically， measure this measure mu of the set of vectors V。

 such that dot product between x and V。Is， at least。Normal x over Delta。

So this probability is at least some absolute constant， positive constant。

And then the second statement is for every T。Leger than 0。Probability of all the reacts。

Such that dot product is not too large。 So it's at most T times normal X。Is at most one over team。

 So let me， let me， let me pass what's written here。 So what I'm saying is that if you。

 if you take any fixed vector in my normal space and you sample a random vector according to this probability measure mu。

Then do product。Would not be too far from the norm of x。So namely。

 thet product with decent probability would not be much smaller than the norm of x。

And for the upper bound side we have a whole tail， so basically like probability that is like t times。

 so we kind of show a khi tail kind of。Thin on this do product between x and V。

 So it's kind of a linear sketch。 It's one measurement， linear sketch。For X。

And after we establish this lemma， the resulting in maing is actually pretty easy。

 Let me what it tell you what it is。😊，And then maybe I'll say two words about。

Proof of this landman maybe maybe I will even not， but so the resulting embedding of of x in L1 minus epsilon is the following。

😊，So I want to embed xent l1 minus epsilon。So let me define what my L1 minus Samson space is here。

So it's a space of functions， so basically in the original space I have points x。

So this is space of functions。And functions are defined on。From， actually， again。Like。

A to the power of dimension of x。Inter real。And let me tell you the mapping。

 The mapping is very simple。 We up X in。Some like mops， too。

So now I need to define a function that takes。A vector from here and obtains the real number。

 And the function is very simple。 V gets mopped into the dot product of V and x。

And so this is the embedding。 it's like almost disappointing。 but the interesting part， of course。

 is that we need to use mu in some way， right so。Basically， when you define like LP space。

 you also have some measure with respect to which you integrate。Like basically here。

 underlying measure is new。So let me explain you what I'm talking about， like what am I writing here。

So basically， L1 minus epsilon norm in the target space is defined as follows。

So let me call this mapping capital F。 and then my。Capital F of x。L1 minus Epsilon norm。

Would be just integral over my。D dimension dimensional。Real space。Of dot product between V andex。

Rise to the power 1 minus epsilon I integrate with respect to measure mule。 So I have like mu。Of D。

 And then I need to raise everything to the power1 over 1 minus Epson。 So this is my。

L1 minus epsilon norm。And then actually， like using these two conditions that I promised you in this lemma。

You can actually show that this integral doesn't deviate too much from。

Normal x lower bound is pretty trivial you just use the first condition and you know。Just say that。

In a significant part of the space this dot product is sufficient wide and we are done so upper bound is a little bit more delicate。

 actually like because of this upper bound we cannot obtain， for example。

 in bedding intel1 so we need this one minus epsilent moment but precisely because we have this cashhi tail and if you know about your random variable that it has cash tail it doesn't even have to have expectation right but it always have this like one minus epsilon moment and that's why we have something nice and bounded there。

😊，So yeah， that's amazing and let me say maybe a couple of words in the remaining six minutes about how do we prove this lema because I think it's pretty nice。

There is no magic here， really。 So it's， it's just， you need to be。So we use。

The following facts about Fourier transforms of random variables。So first of all。

 what can we even use right so we need to use these conditions。

So we remember that time measure is not just some measure。

 but it came from positive definite function that has these properties。

 It's like sufficiently continuous， quantitatively continuous around zero。😊。

But then like at the infinity， it kind of like decays， or at least it doesn't decay。

 but it's not like too close to one， okay？So yeah， so basically the statements that I'm going to use。

 basically it's convenient to okay。If you have random variable。

And if you take dot product of this random variable with a fixed react like we do。

So we'll always fix this x from x once and for all。

And if you take the product of random variable with a fixed vector。

 then in terms of Fourier transforms of characteristic functions。

 it just means that we take a restriction of our characteristic function on a line that passes through x so basically we have our D dimensional space。

😊，And we have like vector x， and then if I take random vector v and take dot product between V and the x。

Then Fourier transform of this dot product is just so it likes psi of T。It's like。

Forier transform of T times x。Sorry， Fourier transform of the original distribution in the point T times x。

 that's just a simple check。So we basically reduce our problem to question about one dimensional random variables and one dimensional characteristic functions like Fourier transforms。

And then we need two facts。嗯。We need the following claim。It's almost a reformation of what we want。

 You know， like if this psi in the point Delta is。Sufficly small。

 So it's like less than one over E in this case。Then。Okay， let me。

 I think I don't have time to properly explain it so I don't want to bo it too badly。

 so let me maybe just say a few words here。嗯。So， okay。

 so intuition is that one of these conditions follow from。So basicallyically， the first condition。

Follows from。The second condition here。And the second condition。

Follows from the first condition here。 And these are like simple calculations。

 So I I I unfortunately， I don't have time to show it to you， but you can actually check it。 It's。

 it's not very hard。 It's written in the paper。 In fact。

 it's like standard in the in the probability literature。

 So there is nothing groundbreaking going on that。 Yeah， okay， so that's it。 I think I'm done。

 I'm almost like， I'm almost perfectly on time。Right thanks a lot Ilia and by the way。

 that other theorem that you had on the slide for a little bit Bner's theorem that's the thing also that I had in mind I know。

Random Fourier features by Rahimian rec for kernel approximation I think is based exactly on Bner's theory it's exactly yeah what I didn't want to go on the record with。

 but yeah yeah yeah yeah it's it's all very related。 Yeah。

 in fact I think it would be nice to kind of compare some of the geometric literature that uses this like inverse Fourier transform for computing this embeddings and this machine learning literature I think there are some parallels that people just didn't even notice so don't even care about or something I think it would be nice。

😊，Thanks a lot， Ellia， I let's give him a round of applause feel free to unmute yourself everyone。

Yes， it takes time to themselves。 Okay， yeah， way that I can quickly unmute everyone just wanted to say that if like if you have any questions。

 I guess you it might be that you have more questions than answers。

 feel free to look at our paper feel free to email me。

 yeah like basically I'm happy to tell you more just like within one and a half hours。

 it's not very easy so。😊。

![](img/8ac5e5dd26af7eedb4c26f21026d3061_3.png)