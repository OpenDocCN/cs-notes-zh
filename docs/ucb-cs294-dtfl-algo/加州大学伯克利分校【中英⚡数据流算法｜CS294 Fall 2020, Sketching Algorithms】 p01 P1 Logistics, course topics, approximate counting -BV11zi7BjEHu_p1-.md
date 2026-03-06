# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p01 P1 Logistics, course topics, approximate counting -BV11zi7BjEHu_p1-

![](img/05a782fec23e134562232fff184127be_0.png)

![](img/05a782fec23e134562232fff184127be_1.png)

Yeahello。😊，Sorry， I meant to record from the beginning because people。

 you not everyone in this era of COVID is in the United States， some people are in other countries。

And。You know they need to have access to a video to be able to watch so sorry that I you know I meant to to auto record I didn't I'll start doing that from the second lecture。

 but for those of you who are online looking at this maybe I'll just make sure that you have this up there's a website there's an email address to email me for the course grading etctera。

 this is all online the grading syllabus is online the grading method it is online etcter。

 the breakdown of grades。Fillling out the Google format I guess the Google form link is only in the zoom chat。

 so if you're watching this on YouTube later or whatever。😊，wherever I put it。

 then email me for the Google Form URL if you haven't already filled it out。Okay。Okay， great。

So let's get started with。Some scientific content or some CS here。

So we're going to start off with streaming。And。Just so we're all on the same page。

 I want to do a really， really simple streaming algorithm， right。

 so that we're nots not completely abstract， which is， you know， example。there's。

 let's say a sequence。Of。Yeah。Sales。And I want to know。Yeah， the gross。Sales amount。In dollars。Yeah。

For today。so my data set is basically this database of a bunch of transactions。

 a bunch of sales that happen today， maybe maybe there are a million sales today。

I only want to know this query this one thing， which is what the gross。

 what was the gross you know money that I brought in for my sales。

 this has the very trivial solution， which is just keep a counter right it starts at zero Every time there's a sale I add in the amount。

So that is a streaming algorithm， Okay， so。Just to make some just to give you something concrete it's not so this is so easy。

嗯。Easy solution。Just keep a running sum。And about like， let's say the number of transactions。

 the number of。Sales， not the total amount， but just how many people bought stuff。 Also easy。Right。

Keep a counter。And if there were a total of n。And transactions。My counter will have only login bits。

Right。So。You know。The first thing that I want to the first problem I want to look at is exactly actually this problem。

 which is just keeping a counter， and I want to show you that actually even there already。

 there's something nontrial。You can actually do better。Okay。If you define the problem。

 if you relax the problem a little bit， which we'll see。So approximate counting。嗯。😊，Basically。

 we have three so we want to maintain a counter end。Subject。To you three operations。

 so this is a data structural problem。So one is in it。Which just sets the counter to zero。

There's increment。Which increments the counter。And there is query。Which just returns the number。

 right， returns， let's say some approximation。To the number。就钱。Okay。Now。

If you wanted an exact algorithm for this problem， then it's not too hard to prove that it's impossible to store like if I tell you is that the number is guaranteed to be between you know zero and T。

Then。It's not hard to prove that you need log Tbits okay I'm memory to be able to solve this problem。

 why because if you're using less than log Tbits， then you know just by the pigeonal principle。

 there are two different numbers。There are two different increment amounts。

That would land your data structure in the same memory configuration。So from the perspective。

 so let's say those two amounts are you know A and B， so if you do a increments。

 you have you'll be in memory your memory configuration look like blah。If you do B increments。

 it'll also look like blah， it'll look exactly the same。

So from the perspective of your data structure， there's no difference。

 so it's going to return the same output for both A and B。But of course。

 at least one of those has to be wrong because A and B are not the same number， right？😡。

So there's no way to solve the problem in less than logarithmic memory if you want a deterministic exact solution。

So we're going to settle for an approximate solution where I don't necessarily want there to be。

I don't necessarily want the exact value of the counter。

 but I'm happy to have it to within say 1% error。Okay。Um， and I'm not going to show it right now。

 but it turns out that even that is too strong and is impossible in logarithmic memory。

But so we're going to add one more level of relaxation。

 which is not only am I willing to allow for1% error。

 I'm also willing to allow for a randomized algorithm。

That has some probability of outputting the wrong answer。Now1% with 1% probability。

 my answer will not be within 1% of the truth。Okay。So good。

 so now what's the best kind of space bound I could hope for？So from a deterministic algorithm。

 you know， I said that it's impossible to have a deterministic algorithm with low memory。

 but let's say we didn't know that yet， what's the best I could hope to have？

In terms of memory consumption， so if I want to know the right answer。What's the best？

Memory that I can。Hope to achieve。Let's say that I'm promised。That， you know。

N is between some0 and t。At query time。Well， let's just look at the powers of one so if I need to have the right answer it's within a 1% error。

 let's look at the powers of 1。01 all the way up to T so okay。

 so there's  zero n could be0 or it could be 1 or it could be you know something that's close to 1。

01 or 1。01 squared 1。01 cubed。1。01 to basically the log based 1。01 of T。So these are all you know。

 other than zero， these are all the different powers of 1。01。That are between1 and T。

RightAnd you know， my true value of n is somewhere in this like line。So this is zero and this is t。

So I know the true value is somewhere here， so let's say know let's say it's here。

Then it's enough for me to return to round it to the closest， you know power of 1。

01 that's near it I could round to this one So this is silly the example because 1。

01 cubed is just roughly 1。03 which is approximately one but you know M could be somewhere in the middle of this line I'll round it to the nearest power of 1。

01 and by that rounding I'm only losing 1% of the value right？So that would be a valid answer。

So you know， in principle， I just need to you know as long as my memory state is storing the closest power of 1。

01 near my value， then that's good enough right so how many powers of 1。01 are there。Up to T， well。

 that's this log base 1。01 of T。So the number of bits of memory I need。 So to remember。To remember。

A number。Up to an integer up to， let's say， log base 1。01 T， I only need。Oh， of。The logarithm。

Of that number of bits。Great。And。So I said you need。So I said log。Of logarithm base 1。01 of T this。

just remember， this thing is the same as。So right， log base。

A of B is the same thing as log B over log A。So this is the log。Of。Log T over。🤧。Log of。I'll call it。

1 plus 。01。And another thing to remember is that basically by Taylor expansion。

 the log of one plus epsilon is roughly epsilon。So。This is basically log or roughly log of。Lg tea。

Divided by。01。Which is log log T。Plus， log of 100。系い。Or more generally， if instead of 1。01。

 if it had been one plus epsilon。If I just said one goes uppsilon， this would have been。What alon。

Okay。So that's kind of maybe the best that。That's something I could strive to achieve in terms of my memory consumption。

 like log log n plus log onrups on bits to store this counter end。Okay。

 and that's what we're going to， in fact， achieve There's going to be another extra term because of。

Because it's a randomized algorithm， there's going to be a dependence in the memory on the failure probability as well。

Okay。And I guess another thing I want to argue too is that not only is this like a。Yeah。

 that actually I can't really hope to achieve much better than this。 and the reason for that is。

You know， if I look at。If I look again at this picture， these powers of 1。01。Let's look at。

 this value， let me use red again。Let's look at this value。And then， this value。

And then just like skip skip to every third one， so skip this， skip this， go to this value。

 skip this， skip this go to this value。Okay。I also claim that kind of the memory configurations。

 you know， if n had been this value here。Verses of N had been this value。

 verse of N had been this value， et cetera。 The memory configurations of the data structure had better be different for those。

 because there is no number that's both。A good 1% approximation， you know。

 it has 1% error for one number and also has 1% error for the other number。Okay。

 so they need different memory configurations so that I can tell them apart。Which means that。

You know， my memory has to be basically。You know， at least my memory has to be missing at least something like。

呃。Log of。I need memory。To be at least log of something like， you know。Log base one plus epsilon of T。

Over three because I skipped every third one。But that that's mega of log base。Log one plus epsilon。T。

So really。 we're going to try to achieve this， but we also can't really hope to achieve much better than this by some additive constant。

So before now I show you。How to do it and you know where this is， you know， and who did it。

 are there any questions about anything I've talked about so far？

So if you're if you're proving this lower bound of log log teeth。

 then that's just sort of like you're going to try to keep the magnitude or something。Yeah。

 I guess I want to keep track of the logarithm。Of the number， yeah。

Loarithm base one plus uppsilon and by the way， I so I do see now sorry， you know。

 one thing that I'll say is if you have a question。Unfortunately。

 I I don't know if it's my version of Zoom or whatever。

 I actually don't get notified when people type in the chat。

So I'm only seeing now that there there have been many questions typed in the chat。

 If you have a question， do feel free to just unmute yourself。And say question。

 and then I'll know that you have a question。Because I won't unfortunately I might not see it if you just put it in the chat。

 so I see there's a question about is the class only one unit？

I believe it's I don't know the answer to that， I believe it's not one unit。

 I mean it should be a number of units which is comparable to a regular course。

And I can check on that。And。嗯。Oh apparently so 294 is in general there are lots of classes that are 294s 294 are basically just special topics graduate courses I guess each one has a different number of units so。

MyMy 294， which is 294-165 should have more than one unit if it doesn't。

 then need to I need to talk to someone and to register and make sure that's fixed。

 but that if it only says one unit that's a bug。嗯。Any other questions about the course or about the stuff I just said for this approximate counting problem？

Yes。Oh so now that I am paying attention， maybe if you have a question。

 raise your hand in the zoom and then' I'll go in that order。Okay， so Serena。Yeah。

 so you mentioned that this algorithm is。Or that you expect us to be wrong。

 like some percent some like proportion of the time， but I'm not seeing where。

That could happen like it seems like。It will be within some yeah。 Yeah， so good。

 So I haven't shown you the algorithm yet。 So what I do what I showed was just kind of a。You know。

Going into trying to design the algorithm， what's the best that we can hope for or what's something that we can reasonably hope for。

 Notice that this business of rounding to the closest power of 1。

01 is not a valid streaming algorithm， because you know the problem is， I don't know N。

 in order to round it to the nearest power of 1。01， I need to know what N is， right。

 But I never am given n up front。 All I'm told is like init。 now I know n is 0。

 And then I'm told increment， increment， increment， increment， you know， some number of times。

And every time an increment happens。I need to make a decision as to how to update my memory state。

So if I'm trying to keep track of the logarithm base 1。01 of n， you know， that's a real number。

 that's not an integer。 So if I'm trying to keep track of like rounding it to the closest integer。

How do I decide， you know， when to increment my my value that I'm storing right so like for example。

Let's say that I'm trying to just keep track of log base two of the number right so let's say the number right now is five。

😡，N is five。And my memory， what I'm storing is log base two of that。Which is two， so I'm storing two。

And then now someone says increment。So N now is 6， but I don't know that it's6， right。

 All I know is I'm storing two。So they said increment， should I increment my two to three？😡。

Or should I stay at two。It's not obvious what to do， right？😡，And then they say increment again。

 now n is seven。ok。😊，Again， all I'm storing is two do I increment at this point or not。

 right and what we're going to see is like the way around this that gives good results is to probabilistically increment。

So whenever I'm storing a value。You know， and someone says increment I'm going to increment with some probability and stay where I am with some probability and that's where the probability is going to come into this。

I see， okay， that makes sense。And I saw there was a question by Robert。

 do you still have that question？Oh yeah。I think I was just going to ask if you could explain why we know you can't do better than like an additive。

Factor better than this again。Oh， then。Mden plus log onerups log。嗯。😊，So I mean。

 maybe let's just say it with powers of， let's say I need to be within power a factor of two of the right answer。

 right？So if you look at the powers of two，1，2，4，8， 16， 32， 64， etc cetera。Okay。

 all I'm saying is look。诶。So。Let's circle some of these numbers one。8。It is good one。

64 and then let's do one more 512。Okay， these numbers that I've circled are boxed。

Orre values that N could take in principle， right。Yeah。And my claim is that。嗯。😊。

Whatever the like let's say we had a deterministic data structure。Let's look at its memory footprint。

 Its memory footprint is just like a bunch of bits。 right， It's just a bit string。

And what I claim is that memory footprint。Had better be different for one if n is1 versus of n is 8。

That better I see storing something different why because it's answer for one if if it's st the same thing for one and eight。

 it's answer for one and eight will be the same right but there is no number that's both within a factor of two of one and eight I see I there is no number that's both within a factor of two of eight and 512 all these numbers had better have different memory states。

RightOkay， that makes sense yeah， so that means that you know in particular in this example。

 my I need。At least four different memory states。嗯哼。😊，For these four box numbers。

 which implies I need at least log for bits of memory， right？So that's all I was saying， I see。

 I see。And that basically will give you a lower bound that looks like this。Okay。

 any final questions before I continue？Okay， imman。Sorry。

 is that a three underneath the log one plus epsilon T？Yes， it is。And it's because I I boxed every。

 you know。Should it have been three， I think。Yeah， because I boxed every third element， so okay。

And then I have a very quick question， if you're enrolled， we don't have to fill out the form， do we？

If you are already enrolled in the course， you do not have to fill out the form。Okay。O可以。Okay。

 so good。 It looks like no one else is raising their hand。 Let's continue for now。嗯。

So the history here。Is basically Rob Morris， there are two Rob Morris is there's the father and the son。

 so the son is a faculty member at MIT and Ekes there， he does systems。

 his father was also a computer scientist who at some point worked at the NSA。

 I think he was like chief scientist at the NSA and then also worked at Bell Labs he was a researcher at Bell Labs。

And there's a nice。Article on this by。His name is Jeremy Lubroso， I'm probably saying his name wrong。

So see article。An archive。By Lobroso。And this was in。In 2018。

It's a it's actually it's a historic so's he's at Princeton in the CS department but this this is not it's not a scientific article it's a historical article where he talks about the history of like where these algorithms came from and why they were being developed so it's a pretty interesting read take a look if you'd like。

Um so。Basically， what he said in that article is， you know why didn' anyone want an approximate counter log n is already quite a small number right for any you know for most values of N that you'll run into why why is it so important that。

You can store it in log log end bits。And this was in the 70s was I think 1978。

 and apparently there was a spell checker program in UniX called Typo。

And the way that it kind of flagged whether it wanted to suggest that some word has a spelling error。

Was it kind of looked at trigrams， so sequence of three letters at a time and counted like all trigrams。

And rare ones， I guess， fed into some statistics calculation it was doing to。

To flag something as potentially a typo if you're typing a trigram that's very uncommon。

 then maybe it's a typo。And。And I guess he didn't have enough memory in those 1978 machines to store counters for all all tri all possible trigram。

 so he needed to squeeze as much， you know。Storage power as he could with his machine。

 so he devised the scheme。嗯。It actually it's。I've actually implemented this myself。

And let me just pull something to show you。So this is not let me share from my laptop。

So people can see this， I hope yet， I think。Good。Yes， so。This is。

Doing on the order of a million increments。 So N got to be as big as a million a million is about 20 bits right and。

What we said here was， let's try and。Storore let's try and store this 20 bit number using only 17 bits Okay so it's not it's it's only a modest savings in our in our memory consumption and we did this experiment。

This is an experiment I did with someone I work with watching you who used to be a postdoc with me and I'll get to why we did this experiment later in lecture。

 there's a reason why we actually did this experiment just this summer for a very particular reason。

But we did the experiment 10，000 times， so remember this is a randomized algorithm so it makes random decisions so 10。

000 times we fed it different randomness each time。

 a different random seed and we incremented the counter you know roughly a million times but we only gave the counter 17 bits to do this okay。

And what you're seeing now on the X axis is。Kind of the percentage of trials of these 10，000 trials。

 what percent bh and what's blah if you look at the y axis。

 it's the relative error from a trial okay so。The max error we ever got was about 2% error when we estimated n。

 So we got a really good approximation of n with 17 bits instead of 20。😡，100% of the time。

 our relative error was less than 2%。 Meanwhile， if you look at， say，60%，60% of the time。

 our relative error was less than what seems to be roughly 03%。

 Okay So that that's what that X axis means， right？ So if there's a dot， if there's a dot here， X， Y。

嗯。😊，If there's a dot here X Y， it means that x percent of the time， our error was y% or less。

There are actually two curves here， there's the orange in the blue。😡，The blue is the Morris counter。

 which I'm about to explain to you from Robert Morris in the 70s。

The orange is so maybe just a sneak preview at what I'll say Susan later is Huing and I actually came up with a new algorithm。

Which we could prove a better bound for than than what was known in the literature for the Morris counter。

 So， and our algorithm was simple enough that we thought， oh， let's。

 let's like actually implement it and compare it to the Morris counter and show that it's better in practice。

 too。 But you can see the results of that this in this plot。 It's not better。 It's not worse。

 It's pretty much exactly the same， so。Anyway， after that， after running this code and seeing this。

 we actually went back and managed to prove a better bound for the Morris counter than what was known before。

So I'm not going to show you that better proof of the Morris counter today。

 but I will tell you what the bound is， okay。So anyway。

 this is something that's actually implementable it wasn't actually too painful for us to implement this。

 it took less than a day to implement this。And it gives you know meaningful results and we actually also did it with like I think instead of giving it 17 bits。

 what happens if you only give it like 13 bits， et cetera， you got pretty decent results。

So this is this is something that is a real a real algorithm， it's not just a big O， no。

Asymptotic analysis algorithm that can never be used。



![](img/05a782fec23e134562232fff184127be_3.png)

🤧Okay， great。So back to math I things。

![](img/05a782fec23e134562232fff184127be_5.png)

I asked a quick question before or in the case of analyzing these to generate the random number。

 presumably， there's like a some kind of pseudoren stream somewhere in the machine。

Would you also analyze the amount of？Memory it takes to due to pseudo randommness or。Yeah。

 so good question like in this for this algorithm I will assume I'm assuming access to perfect randomness。

 so if I want you know， I am assuming that my computer can flip an unbiased coin and get heads with probability a half and tails with probability a half。

嗯。😊，For this particular algorithm。I will never need to remember my previous random choices。

 so you know we're pseudo randomness， we will talk about pseudo randomness later in this course。

 in fact， in the very next lecture on Monday。There are a lot of randomized streaming and sketching algorithms where you know。

 you make a random decision at some point and then in the future you have to make another random decision that's like consistent with some other decision you made in the past。

 for example， like you have a hash function。So you know。

 at some point in the stream you saw you know the item five， you hash it， you got some hash value。

 and then later in the stream you saw five again， so you hash it。

 you had better consistently get the same hash value that you got in the past。

 which means you need to remember your hash function。

And if your hash function is this big random object。And， you know。

 I don't want to spend the memory required to store a big random object。

 So that's where I'm going to need to talk about pseudo randomness。 How do you design hash functions。

 which are not totally random。Because I don't want to spend the memory to store something totally random。

 but they're random enough。That they still work for my algorithm。 Okay。

 so we will talk about pseudo randomness for in that context。 But for this particular mor algorithm。

 because it doesn't need to remember its random decisions。That's not an issue。

 but you're right that there is an issue that I do need to make sure that I have a high quality source of randomness so that the random decisions that I do make are actually uniformly random I'm not going to you know I'm just going to assume that that's that I have that okay。

AllThanks， any other questions？🤧Okay， so。So right， so he developed this algorithm initially as part of this Space Lee spell checker。

 and this was in 1978。And what was the idea， The idea is。嗯h。Let's say I don't store。And。Instead。

 I store a different counter。Which I'll call x。 When I do initialize， I'll set x to 0。

 And when I do increment。I don't always increment X。 I increment x to some probability。

 So let's try the simplest thing， which is I increment x。With probability a half。谁。

So half the time it increments it。And half the time， I dealt an expectation。Now when I do query。

 I need to return what the value is， what am I going to return？😡，Well， the natural thing to return。

Is two times x。Right。Because I expect x to be n over two because I only incremented it half the time。

 so if I return two times x I'm expecting to get a value that's approximately n。

Now what are the pros and cons here？😡，So the pro。I I'm storing。

Probably a smaller number instead of storing Noring N over two。😡。

So story and smaller number takes less memory， right？What are the cons？The first con is。

I'm only saving one bit。Right。N versus n over2 is just one bit of memory difference。And two。

There's now some variance。Right， two times x is not going to it's not guaranteed to equal n。

 It's just something that an expectation is n and there's some probability that this deviates and in fact。

 the probability that I don't get relative error meaning I want let's say I want 1% error。😡，I mean。

 if I only did one increment， then forget it， if I only did one increment。

 I'm definitely not getting one% error because。😡，X is either going to be0 or1。

 I either incremented or didn't increment when I double it， my answer is either going to be0 or2。

 but the true answer is one。 I only did one increment。

 Neither0 nor two are within 1% of one right so I'm basically guaranteed to not get the kind of error that I want to get。

😡，Of course， once I do enough increments， then I'll start getting relative error with good probability。

 but if I did a small number of increments， I won't。😡，Okay。

 so we're going to fix these one at a time and for the first thing I'm going to try to fix is item one。

 the fact that I'm only saving one bit， so let's try and save more bits and then we'll deal with the variance issue later。

So instead。All increment X。With probability1 or two to the x otherwise do nothing。And query。

I'm going to return。Two to the x minus1。嗯。Now好。Why is this a reasonable thing to try。All right。

First of all， before we talk about why this might work。What's the memory consumption。Well。

 let's look at it like this。Once X。And once x。Gets to be as big as。You know， let's say log of。诶。

Is this a good number？🤧。Let's do something like this， yeah。Then。

The probability that I ever increment again。Is that most？嗯。Well， if I do a union bound。

 there are at most n increments remaining， let's say n is the final value of the counter。

 there are most n increments remaining and the probability that I increment in any of them is1 over2 to the x。

 which is delta over n， so this is delta。😡，Right， so kind of with high probability。

 the counter will never get to be bigger than this because once I get to this value。

 it's very unlikely that it'll ever increment it again。😡，And this is basically log。ALo of log。

Ener Delta bits。Which is。Log， log in。Plus， log， log。Whatever Dlta。But focus on this part。Basically。

 it's very unlikely thatll have more I'll ever need to use more than log log inputbits。对。

So we are saving kind of exponentially in our memory instead of login bits using log login bits。

 now why should this work is the real question？So remember what I said？We increment。

X with probability1 over2 to the x， and then query， I said。We output。Two to the x minus1。

And the reason this works claim。Is that。The expectation。Of  two to the x。Is equal to n plus1。

So the thing that we're outputting to。To answer a query is at least an unbiased estimator of the truth。

😡，Okay。嗯。So， maybe let's。Let's prove this claim。So the proof。I's basically by induction。

On the number of increments。Let X N。Be the value， which is a random variable， be the value of x。

After any agreements。Now what do we know know that。X 0 is 0 with probability 1。So。

Two to the x0 is in fact one， which which is0 plus one， it's n plus one， so that's the base case。

 this is the base case。So this is an inductive proof。Now， we'll show that。

The inductive step that will show that the expectation if the expectation of2。

 the Xn is equal to n plus1。That implies that the expectation of2 the x n plus 1 is equal to n plus 2。

Does that make sense？So what do we know， the expectation。Of two to the Xn plus1。Was equal to。🤧。

The sub overall j from0 to infinity， the probability that Xine is equal to J。

Time is the expectation of。Two to the Xn plus1。Given that X n is equal to J。Okay。And what is this。

 this is equal to again， the sum j goes from zero to infinity。

 the probability that x n is equal to J。😊，What is this conditional expectation？Well。嗯。

We know that with probability1 over two to the J， we're going to increment and with probability1 minus1 over two to the j。

 we won't increment。So with probability 1 minus1 over2 to the J。X will stage A。

So then two to the xn plus1 will just be two to the J still。And with probability 2 to the J。

 we will increment it。 so we'll yet。Sorry， this is。1 over2， the J。We will increment it。

And then it will get to the J plus1。Right， so this now in here is just。Two to the J minus1 plus。2。

So this is equal to， I think， right， so2 to the J minus1 plus 2， which is equal to2 to the J plus1。

So this whole summation is equal to。The sum。Over J。Of the probability that x n is equal to J times 1。

Plus。The sum J goes from0 to infinity of the probability that x n is equal to J。Times2 to the J。Now。

 someone anyone tell me。What is that？Just one。 Yeah， that's one， right。

 just the sum of the a sum of probabilities over all if you sum over all possible。

Values that a random variable can take and you take the probability of each， that's just one。

And what's another way of writing this？😡，我认。Expectation of two to the XN。 Yeah。

 this is equal to the expectation of two to the Xn。

 which by our deductive hypothesis is equal to n plus one。So overall。

 this is equal to and1 plus n plus1， which is n plus 2。Which is exactly what I wanted。

So I have the base case and I have the inductive step， so I'm done。What is going on。Weird。

 I can't write on my。嗯。For some reason my iPad is not letting me， my iPad seems to have。Frozen。



![](img/05a782fec23e134562232fff184127be_7.png)

Yeah we go， let's reopen the app。

![](img/05a782fec23e134562232fff184127be_9.png)

hi okay。是。Good enough。 We're done with that page anyway， so we can write on the next page。

 It's good enough。Okay good， so we've computed the expectation。

 the next thing we're going to compute is the variance。嗯。So what do we say。

 we said that the expectation。Two to the XN。Is equal to n plus one， which is why we subtracted one。

 right， remember。If you look here， our output to query was2 to the x minus1。

 the reason we subtracted one is because the expectation is M plus one。

And the next thing we want to do is the variance。So actually， let me write it like this。

So we have an estimator。😡，Our estimator。For n is this N t that I'll call it。

 which is 2 to the x minus1， right？So what we showed really is that the expectation of our estimator is correct。

 it's unbiased， and what we also care about is the variance of our estimator。And let me not do the。

 you know， it's not a very interesting calculation， it's very similar to the one you just saw but。

I will include it in the notes that I put on the website。

 but let me just promise you that this thing is actually the variance of NTilde is actually less than。

Capital n squared over2。It's possible to prove that via very similar kind of inductive argument。

 that will be in the notes。So now how do I use that to get something good for my algorithm to analyze my algorithm。

 I can say， look， what's the probability that my estimator。Diates from the truth。Byuy more than。

Epsilon N。嗯。And you know， this is chubby Cheev's inequality。

 chubby Cheev's inequality says is that most the variance of the estimator。

Over the right hand side square， this is Chevy show。

And I don't want to spend time on these kind of you know taildowns I'll include that in the notes get also that I put up either today or tomorrow just kind of things that I'll assume that you're comfortable with。

Markov's inequality， linear of expectation， chubbyev's inequality and the turn off bound I know that not everyone you know the prere for this course。

Doesn't you know it's CS170 and also some comfort with probability and linear algebra if you' taken those courses you might not have seen the turn off bound but that's okay I mean i'll put it in the notes it's。

ItIt's a probabilistic。Tail bound that tells you a bound on what's the problem that a random variable deviates byhi a lot from its expectation so。

It's something that gives you control on that。Okay， good， and I actually。

 I think maybe I'll say something about it in lecture two in a couple minutes we when we need to use it。

So what is the variance， the variance here， I said is less than n squared over two。

 so that's n squared over two。Epsilon squared n squared。And then of course， the n squares cancel。

And this is。Equal to one over two epsilon squared。Which isn't actually all that great。Okay。🤧U。

If Epsilon， if I set Epsilon to be something like。You know。

 maybe points lets let's think of epsilon as being like maybe 0。75。

Then this is equal to one over two times three quarters squared。Which at least is less than one。

 I think。It's less than one， I think it's less than one， yes。🤧So。So in particular， it's。

Four squared over two times three squared， which is what eight over nine。Okay， so。With probability。

 So this is the probability that I fail。 So I fail probably at most 8 over 9。 That's not great。

 That means I succeed with probability at least one over 9， which is about 11%。 So 11% of the time。

I'm guaranteed to get an answer。 that's at most 75% off from the truth。 Okay。

 that doesn't sound great， but it's something right， It's like it's something non trivial。 I mean。

 if you。A priori， it's not clear to get any decent constant chance of guessing correctly。

But we can of course， do better。So I'll call this algorithm。This algorithm， I'll call。Morris。

And then now let me show you a way to improve it， which is Morris plus。B。What I'll do is I'll run。

Morris。You know， our times。In parallel， each one is making its own random decisions。This gives me。

Estimates。Untilil the1 of2 until the R。And that I'll actually estimate。And as N hat。

 which is the average of these。对。Now。Notice that the expectation of NHAT。Is。

It's the expectation of one over R times the sum of n tilde I goes from one to R by linear expectation。

 this is the same as the expectation of n1 tilde， which we know is just n so this is still an unbiased estimator and the variance。

Of Nha。Is equal to the variance。Of one over R times that sum。

Which is equal to1 over r squared times the variance of the sub。And this is a fact about variances。

 the variance of the sum of independent random variables is the same as the sum of the variances。

 so this is equal to whatever R squared times the sum of the variances。

And we know that each variance is at most n squared over2。😡，Right。So。🤧ううん。

So we know that this is basically now less than。N squared over 2 R。There are of them。

 so it cancels one of the Rs。So we basically decreased our variance by a factor of R。😡。

So now chubbyhamump's inequality says the probability that N hack。

Deeviate someone's expectation by more than epsilon and is that most。

N squared over2 R epsilon squared n squared。Again， this cancels。

And then now I can make sure that this is less than， let's say， some eda。

By picking R appropriately so I can pick R to be at least you know。😡，One over。

Two epsilon squared Eda， I guess something like that。The ceiling of that， if I pick R to be that。

 then this is less than Eta。Okay， so now I actually have a one plus epsilon approximation。

With probability 1 minus eta。But now notice I blew up my memory because I'm writing all of these R copies in parallel。

 so I'm blowing up my memory basically by a factor of R。😡，Okay。

 so I blow my memory by a factor of one or uppsla squared times one over8ta。 so my total memory。

My total memory。Is now something like log， log N over Epsilon squared Eta。

Which is not as good as remember I wanted to get log whatever Epsilon， and I also wanted to get。

 you know this dependence on Ada is not great either。So I can fix this and the way I fix this。

 I'll call mores plus plus。Which as I run。S， independent copies。Of Morris Plus。Each。

With A I day a third。对。😊，And now。Each one of those， you know， so then I get。Basically， N hat one。

N hat S， each of these n hats is an output。Of one of the Morris plus copies。

And then what I'll actually output as my estimate。Is let's call this now n line。

Which is going to be the median。Of all these numbers。So overall。

 our final output is the median of a bunch of memes。😡，And now the claim。Is that the probability。

At n hat minus the actual value of n is bigger than epsilon times n。

Is that most kind of exponentially small？And S， so C is some constant。嗯。Sorry， so not an S。

 but let me actually fix that。So I think that if you want to be precise。

 we can get as we can get two。Let me put a precise number here。Two e to the minus。Epsilon squared。

S over three。So you can pick。It's not going to be three， sorry。There's some constant here。

 we can figure it out later， some constant so you can pick， you can pick S。To be at least， say。

Oh there's no epsilon either， actually。You pick has to be at least say long。Lo of。

C times line of one over Dlta or two over Delta。Oh。

And then this will be basically Western than Delta。没有。So in the total memory。Right。

Willll be R times S times log log T， which is going to be something like or log log n。

 which is something like log log n。Times log whenever delta over epsilon squared。

Which is also not the ideal thing because I want a better dependence on Epsilon instead of what Epsilon squared。

 I want log on Epsilon。But kind of why does this claim hold and the reason is remember're output putting the median。

Okay， now。The median will be a bad estimate if more than half the estimates are bad。

If at least half the estimates are good， then the median will be good， okay。

But how many estimates do we expect to be bad？We expect。An Ata fraction。Of the Edha eyes。To be bad。

Meaning more。Then， Epsilon and error。对。And we picked Ada， how did we pick Ada。

 I said we pick Ada to be。A third。I said eight is a third。So， we expect。S over three。Bad。Estimates。

We need more than S over two bad estimates。For N had to be bad。So that's kind of that's a deviation。

That's a deviation from the expectation。Of at least S over six。From the expectation。

 from the expected number of bad。Copies。嗯。And this is exactly the setup of the turn off bound。 So。

 you know， for those of you who haven't seen the turn off bound yet， I will say something about it。

 So turn off basically says。Say that you have x1 up like XS are independent random variables。

In each of the range zero1。Then the probability that the sum。Of the random variables， X I。

 I goes from one to S deviates from the expectation of the sum。By more than epsilon。

 let's call this mu is the expectation， by more than epsilon mu。Is less than。

Two e to the minus epsilon squared mu over three。For epsilon in the range from zero to1。喂。

So basically for us。You know， you can think that X so for our situation。X I。Is kind of one。If。

And had eye was a bad estimate。It had too much error。And 0， otherwise。Great。

So the sum of the X is the number of estimates that were bad。

What is the expectation of the sum of the X， than it's at most S over3 because we set Ata to be a third。

So we only expect。S over three， we'll expect the sum to be S over three。

What's the probability the sum is bigger than S over 2？😡，Well。

 that means it deviated from its expectation。By kind of， so to go from S over three to S over two。

 you got to deviate by S over six。Which is basically mu over two， it's like half the expectation。

Right， so you got you had exactly this exponentially small failure probability that I was describing that's where this that's where this comes from this you know e to the minus this behavior kind of e to the minus。

S over sometimes some constant。Okay。So that's that's that and this is kind of a generic recipe for designing streaming algorithms right where you first。

 you know you design some random process that describes what your algorithm is doing。

 you show that what you output is an unbiased estimator。Of the true answer。

And now you get some bound on its variance。 That's what we did first right the first thing we did we got a we showed that as an unbiased estimator and we got a bound right here on the variance。

The ban on the variance was not great initially， so we improved it by averaging many copies of our algorithm that blew up the space of the algorithm because now we have to run many copies in parallel。

And then that gives us something， but our dependence on the failure probability wasn't great。

So to improve that， we then。🤧We then took the median of many copies when each one of those copies only had constant failure probability。

 but when you take the median of many of them， you exponentially improve your failure probability。

 you exponentially make your failure probability go down。Okay， so at the end of the day。

Taking the medium of means is getting you a space bound that looks like this。

That's not what I promised you。😡，ok。嗯m。😊，It turns out that the right answer， so。

What I showed you today。We got space， which looks like basically O of。Log。

 log and over epsilon squared times log whenever deelta。Now it's possible to do better。 In fact。

 Morrison his original paper already described how to do better。

 He didn't do this Morris plus and Morris plus plus stuff。

 The reason that I showed you that is it's a very generic way that basically almost always works for any problem。

😡，Okay， so it's a good thing to keep in your toolbox， this idea of meeting of means。

 and there are problems for which the media of means actually does give you an optimal result。

 just not this one。So what did more suggest that's better。

 So a better idea for this particular problem。Is the following。 So what is a determinist counter。

A deterministic counter is so one， an deterministic counter。You always increment， so you increment X。

With probability， I'll call it。1。0 to the x。Today， what do we do？

We implementedcr x with probability 0。5 to the x。Right one over two to the x。

So a natural thing to try。It's in with probability， let's try it to in with probability 0。

99 to the x。ok。收。I'll ask you all。 I claim that there's basically a trade off happening here。 Okay。

 you're trading off memory for。For variance。Okay。So。Which of， you know。

 which of these so going from 。5 to the x to 。99 to the x should that increase my memory or decrease my memory。

 So anyone just unmute yourself and say it increase， right， because I'm increment it more often。

 So I'm storing a bigger number。 So I'm probably using more memory。Meanwhile。

 do you think it increases or decreases the variance？😡，Decreases， decreases， right。

 And even without doing a calculation， that should be intuitive。

 because if I increment with probability 1。0 to the x， I always increment。Then there's zero variance。

 right？Like what I'm storing is always guaranteed to be N with probability1。 There's no variance。

Whereas if I implement with 0。5 to the x， we saw there was some variance。

 The variance of my estimator was n squared over2， right？

 So a natural guess is that the variance smoothly decays as you increase the， you know。

 the base of that exponential。 And in fact， if you do the calculation， it's true。

 You can show that it does decrease okay。So if you do this。We can show。That。嗯。Incrementing。

With probability。W over 1 plus a to the x。Works。For a being something like。Basically。

 epsilon squared times delta。And this leads to。If you analyze it carefully。

 maybe I'll make it a homework problem it needs some memory that looks like log log n plus log one over epsilon plus log one over delta bits of memory。

Okay。😊，So already this was already suggested by Morris and it was kind of rigorously analyzed in a later paper by Flage Jlet a few years later。

Okay。So yeah， that plot that I showed you of Morrison action basically。😊，You get ask。

 what's the optimal bound？Is this optimal and kind of the latest and greatest bound？Is from。June。

 so that's two months ago。 or actually， maybe it's late， maybe it's early July。 So this summer。Is。

Log， log， and plus log， whenever epsilon。 plus log log， whenever Delta。 So the difference is。

 if you didn't notice， the difference is this， right， we improve the the。

Thepsil log whenever Dlta can in fact be log log whenever Dlta。Okay。

And it's possible to actually prove a matching lower bound。 you can prove that there is no algorithm。

😡，That does better than that。Up to a constant factor。To be more precise。

The optimal bound is basically the min。Of this expression and log n。 Of course。

 you can always achieve log n via deterministic counter。So if you tell me that Gelani。

 I want my failure probability to be at most one over two to the two to the two to the two to the n。

Okay， then log， log whatever adult has pretty bad。 It's a pretty big number。

 So at that point I'm going to be like， you know what。

 if you want your failure probability to be that low。

I might as well just give you probability 0 of failure， and I'll give you a deterministic counter。

 So， so that turns out to be the truth， basically。This is the optimal and also same thing with Epsilon if you want your relative error to not be 1%。

 but you want your relative error to be 0。0000001%。😡，Then if it's small enough。

 I'm going to tell you， look， I might as well just give you the exact answer。

So up to a certain point。Kind of this is the best bound。

 but if you want your relative error or your failure probability to be super low。

 at some point it's better to just give me a deterministic counter。Okay。

 so there's both an upper bound and a lower bound。And this was shown actually by myself。

In watching you and we just submitted it so it'll probably be published in 2021。

 but we'll put it on archive shortly。嗯。Yeah， and I guess you saw the plot。 So you saw the story。

 which is， you know， we， we had this algorithm we。We thought， oh， like， okay。

 this our algorithm is not too complicated to implement。

 so we implemented it and it gave exactly the same results as Morris empirically。

And then we went back to Morris and we said， you know what。

 probably people who are not analyzing Morris the right way。

And we went back to Morris and we proved that， in fact， Morris does achieve this bound。

But you don't get this bound just via。You know， looking at the expectation and the variance。

 you you have to do something a little more sophisticated to get this bound for Morris。

 but it's true。So that's all I have for you today， this is the kind of the maybe one of the oldest streaming algorithms that was ever studied counting back from the late 70s and then next week we're going to we're going to look at some more problems as well and more techniques so any questions in the last minute of class。

Oh， I just have a quick question about the previous part。

 So how do we get the like bound on the variance to be in square over 2。Oh yeah。

 I didn't do the calculation did I did do the calculation for the expectation。Right let's right。

 let's let's say let's flip through here where I。去去。Yeah。

 so I did do the calculation for the expectation that was you know right over here。AndLe。嗯。

The calculation for the variance is very similar， it's some inductive proof。嗯。

Ill it's going to be in the notes Okay， I didnt just didn't want to take time in class to do it because it's it's it's just going to take more time and it's it's not。

You're not going to learn anything from it beyond what you saw from the expectation calculation。ok事。

Any other questions？How long did it take you to make the discovery？No de improvement in runtime。

 think。Oh not runtime mean memory Oh yeah， and the memory and how like how long did you work on it？

It was a pretty short project。 I mean， honestly， I think the。I mean。

 it's kind of funny because this this problem has been around since the 70s。

 So why didn't it take until 2020 to improve it， I think the。The problem is people got comfortable。

 you know people just said oh， there's this old algorithm from the 70s we have a pretty good bound on it and why wouldn't this bound be optimal I think maybe people just never even thought never have thought that it's not an optimal bound In fact。

 we fell into that same trap right we also thought that the bound for Morris was optimal。

 which is why we tried to come up with a different algorithm。Only after we experimentally。

 know tried to evaluate it did we realize that Morris itself already achieved this bound。

And once we realized that。Going from that to proving that Morris achieved the bound was a matter of days。

I see。 So now you have a concreteed proof that that's the lowest bound of memory you can achieve。

 right， Oh， how do you prove that you can't do anything better， Yeah， I'm not asking， like。

 how do you actually prove them Then there's a concrete proof right。

 There is a proof that like not just Morris， but there is no algorithm that does better。

There's no algorithm that does better than log log n plus log when reppson plus log log whenever delta。

 that's a lower bound on the performance of any algorithm。



![](img/05a782fec23e134562232fff184127be_11.png)

Sounds cool。Is there a reason to think that it should be log1 over Delta instead of log1 over Delta？



![](img/05a782fec23e134562232fff184127be_13.png)

That's a good question and actually that goes back to maybe the previous student who asked a question why didn't people try to improve it I think the the problem you know it was some kind of like bias。

Lg winner Delta is a very natural bound。 It's the bound that you often get when you look at the dependence on failure probability。

 So I think when people saw that， hey， we have a bound of log winner Delta。

I already showed you basically why the other parts were right I already showed you why log log N plus log winner up was kind of the expected answer。

 right。But I took the different powers of 1。01 that were separated3 apart。

 That was basically that argument。 So that that part was already kind of clearly optimal。

 And then log wave or Delta is what people usually get for most problems。

 And and it's usually optimal。 Okay， so I think that's why people didn't even bother trying to。😔。

Improve the bound， they just assumed of course it's optimal， log1 delta is always the natural answer。

 but it turns out for this problem it's not the right answer。For the the case of two。

 you use the median of meanss and you also do that for the last algorithm， does it make it better？

Well， it's already optimal， so you can't really make it better。 You mean。

 you mean the the the the Morris that the this changing the base of the exponential， so actually。我哋。

We go back。So if you're talking about。If you're talking about this algorithm here right I mean。

 this is just the Morris counter， but instead of incrementing with probability 0。5 to the x。

 you increment with probability， you know like very close to what1 minus some small number to the x 0。

999 to the x right so that algorithm is already optimal right so there's nothing you can do to it to make it any better It's already the best decade to possibly be。

And also， you know it's。Like the reason that you're doing the meeting of means thing， first of all。

 why are you doing the means thing， you're doing the means thing to decrease the variance right but you have to you have to take the mean of one of Epsilon squared of them to decrease the variance。

😡，you have to take the mean of r of them to decrease the variance by a factor of R and for this problem that turns out to be very inefficient memory wise。

😡，A better way to decrease the variance is just change the base of the exponential。For this problem。

I have a question about the lower bound So and what sense is it optimal because you mentioned that we can get better scaling with epsilon by just taking the deter termministic counter right we get worse counting we get worse scaling at n so like how do we know we can't trade off like get a better scaling in terms of epsilon but like trade it off with worse scaling and delta or something I mean okay so first of all。

 how do we know we know because we have a mathematical proof so that's I mean that's so we know that you cannot be this bound but you know。

If we want me to be precise， the the proof says that the optimal bound is the following thing。

 It's the men。Of log n。And log， log n。Plus log on of Repsilon。Plus log， log whenever Dlta。

So like that's the optimal bound， no matter what epsilon delta and NR。😡，That's the best you can do。

 The first term is achieved by a determinist counter。

The second term is achieved by the Morris algorithm by the Morris counter。

I I'm not sure I answered your question Well well maybe to elaborate。

 is there an easy way to like pick between these two on the fly like can you implement an algorithm which kind of。

Does as good as both of these Yeah so the algorithm basically will the very first line will be an if statement right so what does the algorithm get as input the algorithm is input epsilon and Delta。

Well， actually， so that is a good point because。If you don't know what n is ahead of time。

 then you don't know which one to pick。But if I promise you that， you know。

 I promise you that the final value of n will never be bigger than T。😡。

Then you know you you can basically compute these bounds where you replace n with T and then pick the one that's better and then do that algorithm。

 so the first linening your code will be an if。If the first， if log T is smaller。

 than the other thing。😡，I'm just going to do a determin counter else， I'll do the Morriss counter。

Could you also like run both up until you get n and then and then discard the memory but then you're using then your memory is the sum of both right Well only up until up until N right or I I don't know。

Yeah， but， I mean， that's when that's， that's exactly we're trying to avoid， right， I mean。

If I'm using if I'm using memory log n up until the end， like then I'm using memory log n。

 I don't want to use memory log n， I want to use memory log log n。😡，Yeah。

 did the analysis actually use the fact that we have some hypothetical upper bound on capital N So then the algorithm doesn't need to know that。

 So then it's a little unsatisfactory to say the first step would be to check if epsilon and Delta sat some condition depending on T right。

 because the one that you just presented works for any without assumptions on an upper bound。 Yeah。

 that's right。 So that's right。 So if you wanted to actually achieve this upper bound right now。

 maybe I have to think about it for a little bit。 it's not clear to me。

That you can do it without having some kind of knowledge of an upper bound。 It might be possible。

 I just have， I just， it's not immediately obvious to me。Any any final okay。

 so I guess we we have any any more questions， I'm happy to answer questions。

I see there was some in the chat too， let me see what's going on in there。Okay， no， just okay。

So good。I guess I'll see you all on Monday then if there are no more questions。Hey take care。



![](img/05a782fec23e134562232fff184127be_15.png)

Thank you。