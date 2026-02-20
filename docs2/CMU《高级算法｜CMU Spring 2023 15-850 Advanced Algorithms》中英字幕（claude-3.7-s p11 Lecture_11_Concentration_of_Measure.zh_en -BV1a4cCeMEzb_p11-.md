# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p11 Lecture_11_Concentration_of_Measure.zh_en -BV1a4cCeMEzb_p11-

In the past， you know，10 lectures or so you've seen a lot of classical results on。Algorithms。

 you know actually some very modern result as well， but on I would say classical problems。

 you know matchings， min cost spanning trees， shortest paths。A little bit of flows。嗯。

So in the sort next couple of lectures we're going to take a break from that and we're going to just talk about some probabilistic some randomized jas and in particular this phenomenon called concentration of measure which will be very useful for us it's a simple idea but it's a powerful one so you should know it and this manifests itself in the form of。

😊，What we call large deviation bounds。That we want to understand a random variable x。When is it， you。

 suppose the expectation of x is mu。What can we say about the probability that x minus mu？Is。Large。

So I want to say the probability that x deviates a lot from its means。Its small。

And this is really the phenomenon that I want to capture I want to figure out what large is。

 what small is what properties of x will determine various those parameters， how can I quantify them。

 how can I use them algorithm so that's the goal of the next couple of lectures next few lectures I would say so I'm going to give you bounces like this so these I'll call large deviation bounds。

😊，I'll also call these tail bounds so you know the picture I always have in my mind is that the random variable。

😊，Is in this case， let's imagine it's a real value run variable。😊。

And the random variable has some mean and usually this is a picture， you know。

 this is not exactly what's happening that this is the picture I have in my mind the random variable has some mean and theres some measure where it doesn't deviate too much from its mean but。

😊，You know， beyond this。The probability that it's much bigger than its mean or much smaller than its mean is small。

😊，This we usually call the upper tails。And naturally， this one is the lower tail。And in general。

 the distribution function， the density function need not look like that。

 if they might be discrete random variables， it might not be symmetric， things like this。

 but you know that's the picture you should keep on。😊。

This is the phenomenon that we are trying to capture。

So this is these large deviation bounds and I'll give you the canonical ones that we tend to use in algorithm design。

 these are called churn of halfwaying bounds。😊，Again。

 the the providence is dubious but let's not get into that again it's not the topic of discussion today and I'll use this so maybe i'll show you how to prove these and I'll show you how to use these and we'll see how as we are going along which ones we want to do first the proof or the applications。

😊，Can we do this。啊， one为 one。对。So maybe the the the I'll give you the kind of things that we are interested in today we'll be interested in random variables where。

😊，I have a underlying， you know， I have random variables which are。Iither。Independent。

Or somehow weakly correlated。嗯。And I want to understand whether a function of these things， x1， x2。

U to。How does this behave， you know， this function？And often I'll just write this as。F of。X。

And I can talk about its expectation and I can ask for how this function behaves。😊。

Around its expectation， when is it you know is it tightly concentrated around its expectation？

And for most of today's lecture， I'll be interested in the sum function。

 in fact for today' lecture I'll be only interested in the sum function。So F of x。

It's just a sumiggling from one to n。Answer。So in this case， the expectation of。M of facts is just。

个三。I bring from one to end by linearity of expectations。Which I'll just what。你生么快。你话爱贵贵。

And in this lecture， whenever you see a muI， that's the mean。😊，And。In this case， I can say this is。

Thanks。It is just your definition。I'm interested in。

Questions exactly like this now I'll actually say。😊，嗯。Air Force facts。Minus it's mean。

What's the probability that it deviates a lot from its？Questions like this。

 many of you might have seen this before at least so I'll try to not dwell too much on things which are well known。

 but at least I want to make sure that everybody is on the same page。😊，Fairness。Good。Okay。

So know let's without much further ado， I'm going to just get started and。

Maybe the one thing to mention is we are looking for so let me just give you the basic bound so the first bound that most of you must have seen and if you haven't you know what have you been doing but mark of inequality？

Just says for any。Non negative。B variable x。The probability of text is greater than equal to mu。

X is greater than equal to lambda you'll write most one by lambda。嗯。What am I doing， this is crap。

 right？呃。Is that most what？咩啦。That's better。So in particular。

 I could just say x is bigger than twice it's mean。😊，I that must 100。

At most three times it's meaning at most one third。

And it's kind of like a quantitative lake Bobiagon principle， if not every can be above its me。

So you can't the fraction of people who are more than twice the main is that most one。Okay。😊。

So first look question Marco's inequality and in fact。

 essentially if there's one thing that you'll see from this discussion is that everything boils down to Marco's inequality。

😊，This is true for all non negative x。😊，And， in fact。Yeah， let's let's you know。

 which is the other one you might as well tell me the other one。It's Chey shed， right？And I'm using。

One of the 15 different spellings of Chebby shelvess inequality。

I think Shevishaev actually wanted his name to be written as TH， E， B， Y， SH， EFF。

HeEven gave explicit instructions， people just completely ignore it and write it going man unless you're French。

 then maybe you probably write it the right way。😊，啊。Shehebi Sheev was Marle's advisor， think so。

Anyning this。啊。So we have inequality says the probability。😊，Of x minus mu。Is greater than equal to。

Let's say K times。Yes。The standard deviation。He like most one of kissed man。Right。😊。

And you guys remember the proof， right？Let's just。I'll era that after this because I'll need the space。

The probability x minus mu。Is greater than case sigma。Is the same as。

X minus mu squared is bigger than k sigma squared。It is less than equal to the expectation。

Of x minus mean squared。Over k squared Sigma squared。But that's just the definition of this variance。

So， this is from。嗯。Any years。啊。So what did we do， we wanted to showbound。

We applied Markovs inequality， oh， this was Markov's inequality。

We did a transformation of the rhino variable and we applied markers inequality in boom。

Came out the answer。嗯。That's Chey chef。Now， of course， you can start saying， well， actually。

 you know what I'll I can I can also obtain bounds in terms of the fourth moment。I can start writing。

 well， what's the probability that x minus mu？有的。Fourth is bigger than casingma to the fourth and then we'll have to。

こ this。K to the fourth， pig to the fourth， and this gives us another point。😊。

Which in general could be。ATit thenja inequality。These are normal enrollment bounds。In conditional。

If you have a handle on the moment， you can immediately start reading off Mounts like this。当。

How good are these parts， these are you know， pretty good depending on how you what your application is and let's just do a couple of。

😊，Quick applications again， these will be useful。To illustrate。The problem。 So I'll give you。

The first one is just。历 say。X。Is。The binomial。为。N coins each with probability P。应该呃。

This is equal to summation Xi。By going from one to n where each X is just。By no。

It's just a coin clip bit bias speak。Great。😊，This is the same thing and what am I interested in。

 I'm interested in。😊，So let's just do the calculation quickly， what's the mean of x？申请。It's NPp。

What's the variance？O x。Anybody know the variance of text？

N times B times1 minus B n times p times1 minus p。By the way。

 the variance if x and y are independent。Then the variance。

Or x plus y is just the variance of x plus the variance y variance is add as long as the rh variables are independent。

😊，And you can just do the calculation for。One of these guys will be p times 1 minus3 and you just multiply by n because you're taking N ID copies。

对，拜。So what is？Markov saying。Marel says。The probability that x is bigger than。Lambda。

Its less than equal to us。嗯。We can look at a special case。

 let's just look at a special case because maybe you know， let's not get bogged down。

 suppose P one half。😊，Then this is saying the probability that x is bigger than。And over two。

 that's the mean。Times C the diagnosed one over。Okay。😊，Now， of course， x can't be bigger than n。

So this is interesting only for value between one and two。Sy she stay probability x minus n over 2。

Absolute value is bigger than。8 times。The variance。Actually， the standard deviation， right？

So square root of N。Overdo。This is the variance， so the standard deviation is just square root of this quantity。

 which in this case。Is equal to n square root of n over 2。B equals1 half。

And over four square root of that is square root of n element。I won't worry too much about constants。

 but let's just do this in at most one over three squared。😊，And already you see this is much better。

 this is somehow saying that look the expectation。😊，Is a10 over2。

But at n over2 plus about square root 1， the probability mass has fallen to one quarter。

You go two standard deviations， the probability must is dropping quadratically。

S we sha is pretty cool。For many settings， shaby sha is all you need。啊。Good。Okay。

 and then we'll see what battle bound can give us。😊，The saying that the， yeah。

It's dropping quadraically。Okay， let's do one other example。And the one other example is x。Is drawn。

As。Bomial and one over。没有。So exc。Re。Bernoulli one over there。So in this case。Expectation， I mean。

 it's the same thing， it's just a different parameter regime， right？😊，So the expectation of x is1。

And the variance of x is。Pretty much。Like n times one over n times one minus one over n with that master。

Okay。And so really I'm just doing probability， let's not worry about Markov as such you know in this case it's not particularly useful let's look at Chey Che。

So x minus1。I greater than equal to。He times variances。Is less than equal to。One over这 square你们。Okay。

Yeah， it's the same thing。But the sort of instance that I'm interested in is this following instance。

 which is very popular and it's kind of useful as a CS application as well。😊，I have N bins。

And I have these balls that are coming in one by one， think of these as jobs。And balls。

Each ball goes into a random bin uniformly at random。

OkayAnd what I'm interested in is so the load of a bin。Is the number of balls。In the bin。

And the Lord of an assignment。It's just a max。Overall， bins。Of the Lord of the bank。诶。So these balls。

 each the first ball comes in， picks a uniformly random first ball comes in picks a uniformly random win goes to that the second ball。

 the third ball and so on so forth， just independent draws。😊，So each bins load。好。

Ld of a Ben I is behaves like。binomial。And one over end。There are n balls and n bins。

 if you wanted to make this M ball， this n would change to an M。Thatettera。

So what this is saying is that the expected load of a bin is one。😊。

My favorite bin has expected load1。😊，But what I'm interested in is the load of this assignment。😊。

And I'm interested in the expectation of the field。😊，I'm interested in how。

This load deviates from its expectation。I'm not interested in bin5。

 who cares about binI5 I'm interested in the most heavily loaded bin。Okay。By the way。

 do people have guesses on？What be。Expected。Lord。Of an assignment。The assignment。

And Ill say uniformly。A random assignment so this is the assignment by each one of these guys is just uniformly at random independently assigning the balls are being assigned to the bench uniformly at random。

😊，What is the expectation of this load？Under this process， do people have a sense？Constant。

 I'll write down some options， constant。罗嘅。And。Justful。It is very weak thing do。哦，那起来去了不短的露毯。

I know there's a lot of way to do okay。So。😊，Right。Let's look at what Chevissha is telling us。

The probability。That the Lord of any one win。Exceeds， let's say K plus one。

Is that most one over k squared？So the probability that it exceeds you know，10 square root1。

 let's say。Is one over 100。So the probability。Did that exist a been？Whit。Lord。At most。10 square 10。

AvaAC most one over 100 union bound over n Bs。Okay。😊。

So at least you know that with probability at most one over 100 of bin will have load more than 10 square。

😊，And then you can do it for 20， 48 or you know whatever。

 you can use this to show that the expected load of the assignment will be at most square root。😊。

Is this the right answer？I'm sorry。It's with Lord。Thank you。哎。I'm sorry。This is like a bird。

 this is maybe。Not 100% Im not 100% whether I see this， but if， we should talk about it later。😊，Good。

But this is just from a like variance calculation。😊，And actually， you can show， you know。

 there's something called pairway independence。😊，You can just show that as long as any two balls are being sent in an independent fashion from each other。

 even though like jointly， they might be correlated。😊，This bounced in horse。

Se we shall with the second moment。Calculation。It's just looking at pair white things， variants。嗯。

The true answer， so by the way， you know， this can't be the correct answer because we've got a better answer。

 better app or not。😊，啊。So the actual answer is log n and actually you know it's log n。

 but let me not go into that。We expected max load。Under this process of any of the assignment is log n over log log n No this one is not this one will use complete independence and this one will use you know the technology that will develop。

So today we'll develop technology that will allow us to show this with some constants in front again I'm not sweating the constants today。

😊，Okay， so I'll show you that the max load is that most log n over log log in。

This will require a little more effort showing log n will be easy just from the thermal right down boom。

 the answer will come out。😊，Okay。😊，Good。And then maybe if we have time at the end， which， you know。

 I never have time at the end to tell you all the fun stuff， right？So here's the fact， actually。

 let me tell you the fact so that you know， we don't run out of time at the end。😊，A ball comes in。

 let me change the process。😊，A ball comes in， picks two bins uniformly at tri。

Looks at the loads of those two bins goes to the left loaded pair。The power of two choices。

What does the Lord look like now？Expected max load， what expected load of the assigned。二是网络的。

You know the stuff and you shouldn't answer the question I think。

So the correct answer in this case is yeah I chose two bins uniformly trying to went to the less loaded bin。

 the correct answer is log log。😊，And hopefully I'll have time at the end I'll show you a picture。

 I'll show you a proof， I'll show you a picture， it will be proof by picture to make it precise you just need the technology I' have taught you in class。

😊，Anys， okay。So。All that Chebysha got in this setting。

 in this setting of n balls and bins is about square root。😊，So let's view better。So， let's do。啊。

The bound for which I'll erase。This thing。So then I can always keep it around。Okay。

So the bound of interest is called well。It's known in。The jargon。

 at least in in the sort of CSK jargon， but in general， prognos combinators， et cetera。

 it's known as the children ofbound。😊，Or a churn of Hfting bound or a hfting bound or a Bernstein bound or it's look at the notes。

I'll call it a turn off bound。When I don't call it a halfing knot。Okay。

 what's the turn of power the turn of bound says like x1 x2。X先。B。Independent。来个 very books。And。

The range zero1。Their bounded random variables， theyre independent random variables。

I'm interested in S。And， okay。Yeah， yeah。It's S。Which is just the sum of these guys。Okay。😊。

The expectation of S is just the sum of the expectations of Xi。

And let's say that this is equal to me。That's the expectation of that。And each of these。

 you can just imagine there some your。doesn't matter。Then。

I want to show that the probability that you deviate very much。Like S minus。It's mean。

Is bigger than some quantity is small。哎。So here's what I'll show。😊。

I' will show that S minus its' mean。Is bigger than epsilon times than me。Is less than equal to。

Maybe there's a故。Let me do it the following。The probability that s is bigger than one plus epsilon times the mean is small。

我 then。发了。Apsilon。😔，Now I should say then for all epsilon greater than zero。

 the following pixel in epsilon greater than zero， the probability that you deviate from the mean by more than a one class epsilon you know you are above one class epsilon times the mean。

😊，Is smaller。And how small it goes down exponentially。不好。In Epsilon。Okay。😊。

The same kind of boundhole if I ask for one minus epsilon time。Same kind of bondn holes。

And actually I' I'm cheating a little bit， this is epsilon in the range zero to one， let's say。

I'm looking at small deviations， whatever。I'll write down a slightly more nuanced version of this bond later on。

But let's just run with this one。By the way， you know。

 this is one of these bounds that the things that you should memorize just like Marcoovs inequality you can memorize。

😊，Marco's inequality， you can reprove right I wrote some crappy inequality initially and then I realized you know what am I writing。

 you can reprove it right there。😊，This one takes a little bit of proving， but you know， not too much。

 but just memorize it and I'm not asking you to memorize too much。😊。

ItsB O' Donald has this nice thing， he says it's like a poem。Actually。

 I'll give you a more nuance poem memorize that poem this one that one's better than this one so I'll talk about that okay。

😊，Important things do not。I was summing up a bunch of bounded random variabless this is the first time I'm using boundedness Cheishsha was not using any boundedness。

Apart from the fact that it's hidden in the variance calculation element。I'm using independence。

Which really Chbyev was not talking about sums of independent rhino variables。

 it was just x was any rhino variable。Good。Yeah this kind of behavior so let's just look at what this is saying so let's let's you the different colors so that。

😊，I should have used a different color even for Cheby Che。This is saying x minus n over 2。

Is greater than。8 times square root and， let's say。I's less than what？

So what is epsilon in this case？😊，Let me just write it down。Next minus。What's epsilon in this case？

I can write the divide by two asL。Epsilon is。K divided by square root n。Because， you know。

 I can make this this and K divided by square rooting。Same thing。

So epsilon is k divided by squared root 10 squared。Times1 over2。They by three that whatever。

And this is X。Of minus k squared divided1 by6。😔，We have gone from a quadratic decrease。

To an exponential decrease。In fact， a Gaussian leg decrease。I can say。

Often you say the sum of bounded random variables has Gaussian tails。

You kind of behave like a Gaussian， that's the picture we have up there。You remember the Gaussian。

 right， the standard normal rh of variable。Same kind of thing。We love these rhino barrels wherever。

 you know， all Gaussians will love。Okay， so already you're seeing that look the behavior earlier we said oh。

 the sum of random variables， the sum of you know just just a binomial random variable decays fast from its mean。

 if you go out a couple of standard deviations it's dropped a lot。

 but is dropping only quadratically。😊，And now I'm saying is's dropping exponentially。😊，Very情。

In particular， if I wanted a bound of one mobile poly in n， whatever n is。I need to go out only。

And a smaller。I。Much smaller than that。The same thing all care。The probability。That there exists。

 Okay， so let me just era。在 night。Probability。X minus1。Is greater than equal to。

So I'll run into trouble out here。Earlier， I could plug in any K I wanted。喂。😊，Here。

 what's the largest value I can plug in out here？If I just use my turn off paw。

I can set epsilon to one， right？So I can just ask for the question。

 what's the probability that x minus1 is greater than1， it'll give me some crappy amount。😊。

So not so good。Not so useful location here。So let me go back and give you the moment I respond。

The probability。That S is bigger than mu。Plus， some deviation Lada。I that most？Export minus。

Lambda squared over2 numer lambda。😔，怎么。And the probability that s is less than actually。

 I don't need to give you a lower tail because the lower tail you'd never care for epsilon bigger than more。

The probability of being negative is zero， these random of variables are。Positive。

So this is a battle bound。对。Let's just very quickly check。This bound implies this bond。Actually。

 don't worry about taking this bound implies that part。That's not talk。Yes。So here。😊，Now。

 I want to say what's the probability that my deviation is bigger than let's say。😊，Login。

let say诶快译逻嘅。I'm looking at my favorite bin。And I'm saying what's the probability that I deviate from my mean。

 which is one by more than five log n？This is at most x of minus。Lambda squared。5，25。Log square n。

 divided by。Mcleus lambda， mu is one，2 mu2。Plus five login。没。😊，There's some garbage constantsling。

The login term is the operative one。Log squared divided by log。Still leaves the log。

E to the minus log is 1 over。暴裂。The probability that any bin。

 the probability that a fixed bin will have load more than 5 log n is one over poly。😊。

And maybe I'll make it even one over end square。One over two n would be enough， but one over that。哎。

😊，So the probability that there exists a bin with more than five log n bins。

 five login balls is less than one over end。😊，你're done。You've just shown an upper bound of log n。

On the lawn。So you're gone from square root there lawyer。S， yeah。

Kind of once you have the right tools， a lot of these proofs become very simple。😊，We good at this。

Again， no rocket science， I've just given you a random proof out of nowhere or a random theorem out of nowhere。

 I haven't even proved it。But you'll see。Two things you'll see that the proofs going to be very simple。

In fact， you know， yeah。And the second thing you'll see is that the applications of this are you know。

 every so you'll you'll just。😊，呃 yeah。You'll be able to'll be stuck in a corner and then you'll say。

 oh， turn up pounds。听明。It's going to be just like that。Okay。怪性子。If not， then we can take。

An early five minute break， whatever have a two minute break today and。We can will continue out。O。😊。

So let's let's do a。Let's do the application first。So I'm going to use。Ch up bonds。To give you。

 to tell you about。Something。Oh。Loouting on a hyperc。So you guys know what a hypercube is， I assume。

不。A hyper cubebe， which I often write as Q sub D。Is just the set of all， you know。

 it's a set of2 to the N， it has2 to the N ver series。😊。

And the vertC are just indexed by big sectors。Or size D。And then the edges。

Are between bit vectors x and x prime such that x and x prime differ。In one bit。有的。哎。Okay， 할不。

What's the problem I want to solve， I want to solve the following routing problem。😊。

Every verortex of the hypercube。whatever you did every verortex has a little packet sitting at it。

 let's call the packet P go I'll never know。I won't ever refer to it。Okay。

 this packet wants to go to some destination。拜又快。every one of these verticCs has a packet it wants to send to somebody else。

😊，P is a permutation。So I have n I have oh， maybe I should have just said n is due to the D。

N is the number of words you see of this hypercue。There are n packets sitting initially at all the distinct vertices of the cube。

 they all need to go to end destination。😊，バイナス。Okay。Packets travel。On the edge of the cube。

Every edge of the cube。Is really， you should think of it as bidirect edges so every edge and this could be 01。

1，01 and this could be 01，100， let's say。These are my directed edges。This vertex。😊。

On each of its edges。😡，It has five edges coming out of it， right d equals five。😊。

On each of its edges， it can send out one packet。😊，So a packet can travel on this。

 it has some other edge a packet can travel on that， but one packet can travel at most。😊，对。Now。

 what might happen at some point in time is that this vertex has a whole bunch of packets that have come to it。

So it maintains a queue。And you know the letter queue is already taken so this is a waitinging queue。

😊，And then the queue for every edge so in fact you should forget about all these things and for a single edge and this is I'm looking at the edge going from 01101 to 011000 this edge E has a weighting QWE which looks like this。

😊，Okay。Whenever a packet comes in， it enters the queue。😊，And at each point in time。

 this vertex takes out one packet from the front of the Q and sulatorton。😊。

If there's no packets in the queue， there's nothing to do。Okay。😊。

Absolutely so it's my direct so this this vertex on this edge is doing something its own thing and this vertex on other edges is doing its own thing as well let's not worry about that basically for an edge I have a cube。

😊，And if a packet wants to traverse that edge。It joins the queue and the first packet and the queue leaves and goes。

very simple routeuting。😊，Very natural wrote。Okay。😊，对。The problem clear。😮。

It's like discrete time steps， good discrete time steps。

Synchronous discrete time steps so it doesn't matter if multiple things come into this guy。

 let them enter in some arbitrary order。😊，I mean， like it might actually matter yeah， it might。

 but it won't and we won't worry about it。We we'll cross that bridge when we come to it。

Is more nuclear。What do I want， I want that all the packets reach their destinations as fast as possible。

Actually， I don't know about as fast as possible， but I want to make sure that the packets reach the destination and at most let's say。

😊，You know what's？these steps seems you know， kind of essential in the worst case。

I'll say 1 these steps。That would be great。Good。Good， okay， so now that we are clear on the model。

 let me propose。😊，An algorithm， which is called bit fixing。😊。

And suppose the packet wants to go from 01101 to 10001。So。It'll look at its this is the start。

 this is I， and this is pi of phi。😊，So the packet for C is look my first bit differs from where I want to be。

 so I want to fix that bit， so Ill go to 11101。The first bit is fixed。

Then it see I need to fix the second bit 10101。The first two bits are'll correct now。

 it says a third bit needs fixing 100。That's actually， that's it。

The next topic reached its destination。It goes from left to right。And it fixes bits。Quick fixing。啊。😮。

Is bit fixing good or bad？Is it a good al， it's bad yeah， why what's an example？Ply。

 they all try to use the same set of edges， the edges that you in it and same kind through your hockey。

Anybody have a concrete lower bond that you can think of？More about the。

Like what are we choosing or what are we choosing so in this case if I'm using data fixing I'm not choosing anything I'm just trying to。

So in general， I could I want to choose the paths， bit fixing is one possible path to get from eye to pifying。

I could choose any paths I wanted， but that's fine。So I good so one thing you know。

 I could do various thing， I could say， oh， my strategy consists of choosing a path and choosing a schedule for it。

W says， oh， go to that vertex， wait for seven seconds。😊。

Let's imagine things happen once every second。And then go there and do something。

 and go there and do something。YouIt could be very complicated。I want， let's say， you know。

 Dessie Durata， I want a simple act。That achieves low latency by latency。

 I mean the time from where when the packets start。And remember the panel。

And when all the packets have been delivered， bless you。Well of course the based on pie。

 the optimals came might be extremely complicated my case stream comment here's some simple random and that would be very nice。

Let's keep our goals high。Goal is clear。Big fixing， is it bad？It seems kind of bad。

So let me show you an example why bit fixing is bad。

so let's consider a permutation remember this is the worst case bound I'm really interested in I want to say for any pi with high probability this my strategy should succeed in bit fixing you know there's no probability。

😊，For any pie， my strategy should be good and I'll show you that there exists bias for which this strategy is crap。

😊，Okay， and let's consider the following thing， so let's look at。😊，Pies。

 which look like the following。So consider all words of the form W followed by serons。

These will be the start wordtics。😊，And each such guy wants to send so if this is I。

Phi of phi is going to be zero。波伦比得。Okay。😊，Oh， both of these are side B over2。😡。

So how many such packets are there？2 to the D over  two， which is look。

All these packets have to go through the vertex0。😊，You'll start fixing bits from left to right。越嚟车。

You have fixed all these bits to zero， you are still not yet fixed these bits。😊。

All of these will go through the vertex0。There are so many guys who are going through a single vertex。

 this poor smuck can only send out D packets every time。😊。

So the amount of time taken will be2 to the D over two divided by the at least。

And this is not even taken into account that sometimes he might have fewer than the packets。

 you know， things like that， other times they might be more， whatever。😊，That's a lot of time， that's。

 you know， whatever。So this is like square root n over log。I wanted D。Not good。Okay。😊。

So let me give you an algorithm。So this is one I。尿度。Valiant。And valiant in Brener。

I don't quite again know the Pronce of you know how exactly it came about。

 I meant to look it up and I got it distracting。So everybody happy so far， and here's the algorithm。

For each eye。b呃。Random。Vortex or I。From the queue。Okay。😊，声。I I， so for all I。Send I to our using。

Big fixing。O。😊，啊。Then at time five weeks。看。I'm hoping that at time 5 d， everythings finished。

 I'll show you that， you know this will be good at time 5 d at 5 d time。😊，声。From our。Goodbye or fine。

Using big fixing。So pick random a midpoint。Send from I and then send from Arol I。Just curious。

 think this is slightly more complicated than maybe the first naive this one I think about is something randomizeding random bit fixing right？

😊，鬼关系。So pick the order of。The bits。Pick the order in which you should fix the bits， right？

Let me think about that， don't know。I think it fails， but I don't know。我。So the question is。

 here' a different algorithm？😊，Instead of fixing bits from left to right。

Pick a random per mutationut on the bits。And fix the bits in that one。啊。

SoSo I was imagining one random permutation for all of them。😊。

Now one thing that happens is that becomes a centralized process， we could talk about that。

 but you know whatever， maybe it's not important， I don't know of the answer to that。Okay， of。

 instructorstruct report，Would not work。Okay， so you know， we'll talk about this little hammer。

We'll answer your questions soon， if not right now on PR。Where。

Under humanating a bit of extra self inside each。there's a bit of inefficiency let me pause discussion on this one to be answered。

😊，Not to be left aside。But let's look at this one。Okay， good。Random midpoint。Yeah。So really。

 I'm going to show you the theorem is going to be， I'll write it here even though this will get hidden。

 so maybe I should write it here。😊，The Tem is going to be it。With high probability。All packet。Wach。

All right。And。At most，50 bank steps。哎。😊，So I'm basically just showing you the first part。

The second part is going to be pretty much exactly the same。

 I'm not going to argue that it's pretty much a symmetric process。😊，嗯。Good。

 so let me let me show you that this first time step this this first phase should。

And with high probability by 50 steps。Yeah，Oh。哎。Roth。Okay， so how is this going to proceed？Yeah。

 that's for war what that thats for award stream example。That's what the worst case yeah。

 so for any possible pie， fix a pie。Then if RI are chosen randomly and this is really with high probability over the choice of Rri over the random。

😊，Over running。啊来。For any pie I fix the pie。Yeah。Yes， each buyer has to every eye。

 otherwise if you would run into trouble， basically everybody wants to go to the same place。

 there'll be a long queue。😊，Little bottleneck out there。

 so this is why permutation routing was important。嗯。Good。Okay， so let's prove this guy。😊，So。

So how am I going to prove this？😮，I'm going to prove， I'm going to write down you know。

 two or three claims and then we'll prove them。So let's say that PI and this is capital PI forget the fact that packet I was called little PI not important I've already forgotten that capital PI is the path。

😊，rong。百度啊。It has a bunch of edges， you one， you two。不在。对。So I want to show。What is so first of all。

 you know， claim one。That be expected。Number of parts。Using。Bch。E， what any edge。

Is that most something what's the expect， by the way， what's the expected length of a path？

W do you have of view deal。Right。😊，So the expected length of a pass is B over2。

So how what's the expected number of edges being used so you know this was d over two lengths for every part。

 there are2 to the D。😊，Many。Page being sent。So this is the total expected length of all the parts。😊。

How many edges are there in the cube？D times 2 to the D because you know， edges are bidirect。

So every guy has D edges coming out of D times two to the day。

So the expected number of path oh and everything is symmetric， right？😊。

There's normal asymmetry in the process。So the expected number of parts using an is not。

So in expectation， the number of parts using me is very small。And already， you should be， happy。

 you're like， oh， the expectation is small。Tournal punishment。Well use journal on somewhere。ok。😊，七对。

So then。But you know we'll have to so be a little careful about that。听唔度。

Let me just make sure I get the claims right。啊。Oh yeah， so claim two。

 let's look at any two big fixing path， so this is you know path one。😊。

Can it be that part two joints meets this part goes here， comes back， joins again？

My claim is this cannot happen。We are a bit fixing from left to right。

So claim two is just that this does not happen。明了。BI and PJ。边 percent。And at most one。Contguuous。晒。

But's me。They stay together and language much。Pin three。

 and this is going to be the really interesting plan。Claim3 is going to be。delaylay。Od。Thank it， hie。

Is going to be the length of its spot。Plus。Is at most。The length of its part。Plus， what's this。

 so I'll say SI。Where。SI is the set of J such that Pj interects the light。

Every part that intersects me。Can delay me by one。诶。And then the claim four will be。That the。

With high probability， the size of S will be less than me 4D。Was with high probability， okay。

 the probability that there exists in I such that S bigger than 4D is less than one over n squared or something like this。

The probability that there exists。😊，Large intersection for some。His dining。嗯。😊，So better。

 then it may be used to all the PIs。You can imagine any strategyYeah so you could say。

 well I'm doing bit fixing in the sort of more interesting ways you're starting to go towards Keegan's idea of maybe doing random bit fixing and so here I'll use the I'll use the proof a little bit。

 but maybe we'll see how I'm using bit fixing okay。😊，Maybe just an canonical path might be enough。

 we'll see。So claim one， we just did the calculation。Claim one is done claim two。

Kind of proof by picture or you know I convinced you I bullied you into believing that this should be happening claim to a true come on it's Friday。

I'm using well， come on guys， it's Friday proof。Clame three is going to be the you know interesting one。

 claim four is also interesting because you know we do some churn power finally。😊，Okay。😊。

So let's prove claim three。A delay for a packet is at most its length， which is necessary， I mean。

 come on guys， it has to travel this path plus。😊，One for every atmost one。

 for every other packet whose path intersects mind。So let's prove claim three。哎。😊，I'm fixing。

The pots。博拜。And I was。Focus on， in fact， let me this too。Having drawn all this。

 let me erase all this and let me see， remember the path was E1 E2 up to Ek。😊，Actually。

 I'll use the notation because I was just fixing the notation。EL， L for length。This is E。

This is one particular edge。Okay。😊，Look at some time T， so what's the argument？

So the argument is every time， you know， what's happening？Is there're the queue for this edge。😊。

Why would I be delayed， I packetti？I am packet no， I packet， okay， why would I be delayed？

I is delayed if it's sitting in this queue and there are people in front of it in the queue。😊。

Its delay is going up。It wants to blame somebody。Now you are responsible for me。I want to ensure。

That I blame。A unique person for every increment in MIy life。And then I'll have done this。

 so a unique person whose path intersects mine and I can't just blame that person I don't like their face。

😊，They should be responsible for me somehow。So eyes sitting here。It's getting delayed。

 somebody's dealing。So let me just introduce some notation which will be useful。😊，啊。A packetache。

 any packet， not just I。Has。Lag。Okay， so suppose this packet is sitting here。😊，In front of Ek。At。

So this packet， J is sitting here。This packet has lag。P minus k。If it is。Really。To cross。いけ。系对。

At the beginning of time T， look at all the people who are sitting in this queue。

 they are ready to cross this queue。😊，They're ready to cross this edge。They all have a lag。

At this time。Okay。So let's look at packet it。My packet， packet I。And let's look at E1。At time one。

 it's ready to cross this edge。What will its lag be， it's time one？Edgege E1，1 minus1 is0。

So initially this packet has lags zero。😊，Backet I have legs there。It's going along。

 it still has like zero， finally， you know it has to wait。😊，For some more time。

 its lag goes up because p goes up and it did not move along that edge。😊。

So the lag of a packet captures how late or the lag of this packet。

 packet I is going to capture when it's going to reach。😊，The destination。Yeah。

So I want to show so the claim is suppose the lag of packet。I went from L to L plus1。

It wants to blame somebody。Who should it be， it's sitting in the queue， right？😊。

At time tea or whatever。L corresponding to L is t minus k。It's sitting in this queue。

If it moves along this edge。😡，It's going to be。At Ek plus1 x T plus one。Its lag has not one up。Okay。

😊，So I， if it moves along this edge。😊，Its flag will not go up。But suppose it doesn't move along。

It's sitting here。Some other smuck went along this。Hch。What was that person's lag at the beginning？

Also诶。Because remember， any packet has lagged t minus k if it's sitting in this cube at the beginning of tanky。

That's the definition of lag。The lag is， you know， if you're sitting in queue for EK。At time T。

 your lag is t minus k。嗯。So this other J， which was fitting in there， decided to go along。I blame it。

You were the one responsible。Now， suppose Jay leaves this path。When J leaves this spot with lag L。

Will blame you。So I want to claim that if I my lag went up my as an I。

 I's lag went up from L to L plus 1。😊，It will blame some packet which will leave this path。

 this magical path。第二。With lag L。If eyes's like went from L to L plus one， it' will blame somebody。😊。

Who left the spot with Gar。So let's look at one case， I was blocked by J。😊。

Jay immediately left after that。It left with Lael because it had Lael when it crossed。

It didn't have a chance for its lag to go up， it just left。Okay。😊，Now。

 what might happen is they might get stuck in the next queue。But it had La L in this queue。

Everybody had Lael in this gear。So if it didn't move some other J prime across this edge at Laar。

That's the one to blame。Maybe that guy goes for a couple of time steps in their leaves。

So the invariant we are maintaining is that whenever you know， I was delayed because of J。

 then J had LaA。😊，If J's lag went up， there was some other J prime which had lag out。😊。

And this keeps on going until somebody either the you know QNs in which case you you know trivially leave the end of the queue or whatever this path ends。

 you trivially leave the end of the path or this packet just takes off。😊，So the claim is。

That exists as unique。Backacket。JNSI。Such that Jade leaves。The pop the。With。你来没有。Give this。

So every time our lag went up by one， somebody left with a unique lag value。

And you blame that person。Did that kind of make sense？

Why can't you have someone who went in their leg like tenets and then eat that later like I come in and always see them with leg？

Sorry I didn't quite cast like lack can never reduce。😊，But it's like someone comes in with light。Oh。

 someone comes in and to like them okay， right okay。

 we have like them everybody in this thing is like them okay。

 then I'm still having guarantee that later I come in the you。So that person now has。来就去。

Or are they soon？So anybody who's sitting in this queue waiting to cross this edge。

At time T has t minus。That that。So if they continue to be in this queue， their lag is only going up。

Yeah， so in this case， I blames J。一个。So I will blame Jay。

But then J got delayed itself because of J prime， so I transfers the blame to J prime。Because Dave。

 you know。So here is how I you know， keep in mind， look， I and J have the same lag。

I got delayed by J。Jay's lag remained ill because it moved one step further。

And there's one time for them。So it's lag here。Is going to be？带了行。So if it's lag as L。

 everybody' is laing this single cell。😊，Now， if it got delayed， if it's J got held up by J prime。

J prime's initial laggo there。It still remains itself。And then it remains out。So in this case。

 I says oh， J prime left the queue。😊，J Prime left this spot with lag。Clearly。

 I've confused you guys completely。But this is very cute， but。哎。Let me。Sugest the following。呃。

Let me put a question mark out here， you guys tell me whether you would like me to do the proof again next time。

Have a look at the notess。Let me just do the last bit， which is the probability that there'。

 you know， that any of these intersections is very large is small。😊。

And this is going to be where you know， really all the action should be in the turn off bound I'm spending most of my time on the on the combinatorial bond。

 so let me just give the turn off bound down here。😊，And。So what do I want to show？I want to show。

So remember， I want to show claim thought。The probability。Read the size of S。

Is bigger than let's say forward B。Is less than one over。And。Cumed。Therefore。

 the probability that there exists in I such that SiI is bigger than 4D。Is one on that one school。

This is just a union board。So I just need to prove this thing。Okay， both。What is I？SI is just saying。

Whether。J intersects I or not。 I'm counting the expected number of。 However。

 I'm counting the number of people who intersect。啊。I。Okay。Good。What's this sign？

The side of fasci is the sun over edges。In the but。Of the number。offff。Interssections。Or， actually。

 I should say at most on。Edge E。见。Look at the first stage of my path。How many people intersect this？

Ha。In expectation。But let's just look at the number of intersections on the AGK。

How many parts intersect the first stage， how many parts intersect the second age and so on so forth？

😊，三で三。This is actually its right now this is a random variable， the number of intersections on IGK。

 the random variable。😊，诶。😊，And so the total number of parts that intersect me is at most this much because I'm just counting the total number of intersections。

 the total length of intersection。😊，So S。Is。So the expectation。我S i。

A at most the expectation of this， so this is atmost d over  two because the length of the path can be at most be。

This is umost de。Okay。然后。What do I want， so I want to say what's the probability。

That the size of that。 by the way， what is the。As I， sorry， what's happening？Thatect。Y。

 no hang on just one thing。嗯。SI。Is at most this much。

 but you SI is just the sum over all parts J not equal to I of the indicator of whether P and Pj。

Intersect。去。😊，This is the right available。Because PI and PJ are both rank。This is a random variable。

 so S is the sum of random variables。Are the bounded random variables， Yes。

 there are01 value random variables。So they are all bounded。Are they independent？Why not。B i。And PJ。

You know， everybody is choosing their destinations independently。So whether PI intersect with PJ。😊。

And PI intersect with PK， these are independently chosen。Oh was an RI of mutation at？No。

 no RI was just independently chosen uniformly at rhino。Okay。

 SI is a bunch of independent random variables which are all bounded。😊。

Its expectation is at most d over2。Byu the turn of pound。

The probability that SI is bigger than its mean。Which is at most d over2， this is the mean。Plus。

 let's say four times D。Iect most。X of minus。The 16 d squared over。Do mean plus whatever。

Or leave something like this。Doesn't matter。But really。

 this will be at most E x or minus something like some constant times D。Days like login。

So this is like next。Of minus some constant times flow again。

Make the constant large enough so that this has gone over damage。Yeah。That's pretty much it， okay。

Let me just。七八平。Okay。😊，So you know on next week， maybe if you guys want。

 we'll go over the proof of the delaylemma， it's there in the notes as well。

 but and if not we'll do other applications of turn of pounds in particular I want to talk about this idea of dimension reduction。

And the。Johnson Lyinden Straussma for dement reduction。

Just kind of a powerful idea that you should know about good， I'll see you guys have a good weekend。

😊。