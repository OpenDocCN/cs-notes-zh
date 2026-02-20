# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p12 Lecture_12_Concentration_of_Measure_II.zh_en -BV1a4cCeMEzb_p12-

咁大。Glorious day。Almost。I feel like we should have lectures outside。

 but I don't know if we are set up for that kind of thing。啊。对。So let's start off on with some slides。

 I wanted to show you the charging argument of Valt and Bner。

 it's a very simple idea last time I think。😊，Not being clear， I'm sorry。Okay。

So if you remember the setting， we had packets in the hypercbe。😊，呃。

The hyperQ was not particularly important in that case， at least for this part。

 I just need to make sure that a packet I needs to go from this red node on the left to the gray node on the right using some path。

😊，And let SI be the set of packets， other packets whose path uses at least one edge on this this particular path PI。

😊，And then the theorem we wanted to show was that packet I reaches its destination at time at most P。

 the length of the path plus S， the number of other interfering pack。

That is more or less a packet should not interfere with I more than once morally， that's the thing。😊。

And formally， heres what we ensure。😊，Packet I will generate a token。For every unit of delay。

 every time it's delayed， it is generated to。This token。Will be carried by some packing。You know。

 it will generate a token and say you are responsible。 here the packet， the token for you。

You might give it to other people that's all right， but every token will be carried by some package。

😊，Now， your part， might E P。But when you leave。You will be carrying and in fact。

 at any point in time， a packet can be carrying at most one token。

So there are S I different other packets。 Each of them will leave this path or reach their destination carrying one token each。

 So the total number of tokens that they they there can be in the system are at most S。

That's the argument。And this is what I want to show for using this animation。

Is the general proof idea clear？There's a bo。Every time I is delayed， he will generate a token。

 they will say you are responsible here， take a token。😊，Every token will be carried by some packet。

Every packet will carry at most one too。So the total delay that I can have is that most the number of other number of other packets。

 which is at most S I。ok。So that's the main idea and let me just show you a proof。Packets。

 so there are these。Acuses， one for each edge。Backackets in queue。K have lag k minus t。

 so they are the time which is on the right， there is the Q number which is written out there。

And packets in Q1 at time1 have lag zero。Packets in Q2 at time 1 have lagged -1。

They are ahead of the game。Whatever。So packetit I is sitting at its origin at the beginning。😊。

And there are a bunch of other packets。So let's look at what happens。啊。Act time 1。Back it to move。

And I'll do it slowly you know step by step。 So look at the last queue。😊。

D is at the head of the packet。 It just ahead of the Q。 It just goes ahead。

 It goes wherever it wants to go。 And it goes to the gray node。 and it's maybe move on。

 I don't really care about it anymore。Look at this cu。B that the head。

 it moves the third Q C remains。Now comes the interesting part。I is not at the head of the queue。

 so I is going to be delayed。😊，If it's delayed， it generates a token。And this token。Is do numbers0。

And it gives it to C saying you you were in front of me， remember， it gives it to A it says。

 you know， A， you were in front of me， you stopped me。Here's the token for。Now， A is carrying I took。

Okay。Token0 created because a was transmitted， I was delayed。😊，And then maybe some other， you know。

 this is the end of time1 pretty much there might be some other package that might come from the outside the system that's okay F and G were added to these cues from outside this。

😊，And now。Time1 ends。Thank you。B goes ahead。 G is hanging around。 no big deal。

 Nothing' is really happening。 Let's look at this one。AA is carrying a token。

 but it is getting delayed。😊，What it does is it tells C C here， you know， take the token。😊。

You're dealing me。So the token somehow is moving at unit speed through the net。와。So。It gives it to C。

 and now C is getting the two。Remember， a was carrying the token， now C is carrying the token。

And here， you know I at the front of the queue adjustment。Very enough。Good。Thank you adds。

Saing nobody else came in from outside。 I got tired of making animation。Okay，93。Last。

 let's look at this queue。C itself is is delayed by G now G is going to go ahead and C is going to give this token you know it say take it this token should move it unit it speed through the net。

😊，Okay。Token 0 is transferred from C to G because C is delayed by G whatever。Next。

Who's going to move？A Elmo。And it will get a token and the token is number one。Okay。

And this is keeping track of how much delay I have seen。😊，And now you can do this yourself。

 it's very easy。This time， C is going to move。He will give the token to say。嗯。I is going to move。Oh。

 by the way， there's one thing I should have mentioned。A had previously received a token from I。😊。

A receives another token from I。 In some sense， A has delayed I before A is dealing I further。😊。

That's okay。O。I you know generates a token， give the to f because it is delayed and maybe F doesnt join that queue maybe F is going on some other queue that's okay。

😊，So F but F takes a token when it leaves。😊，It's carrying a to。I'm scanning at most1， too。That's it。

 you know， this thing goes on。Other arrivals might happen。 I gets delayed again。

 I generate another token。And finally， I reaches。4 tokens were generated。明白。The arrival time is7。

 which is the part length plus the number of programs。So basically。

 the point I want to make is every time you are delayed， you generate a token。😊。

The token is carried by one packet， the packet。No packet。 You know。

 every token is carried by a packet。 every packet carries with most one token when it leaves。😊。

And that's pretty much the recent proof。So this is one of these charging arguments you should be comfortable with charging arguments。

 They are very you know ubiquitous they come up all the time。😊。

I also rero the lecture notess so hopefully you can read it and you can get it and that shows the that shows Valal argument so maybe I'll just write down where we are lecture 12 we are still doing concentration。

And I want to just finish valance。Charging argument。

Feel free to have a look at it and if you have questions， post together， catch me。

 come by office hours and we can discuss it further。😊，So but for today， the rest of the time。

 let's go back to churn off whatever concentration bounds， I'll talk a little bit about the proof。

And we'll talk about it in two ways。嗯。Then maybe a little bit about extensions of churnoff bombs。

And then finally， if there is time。Hopefully I'll get with dimension reduction。

Which is really another turn of pound。啊。Just going。Actually， squares of Gaings。

So mean talk about this。Because of now， let me。Turn both of these off。And go back to。



![](img/3c2b9e06e98b42ddc6ae9ada965db63c_1.png)

The board。And maybe what I'm going to do is I'm going to write down the。



![](img/3c2b9e06e98b42ddc6ae9ada965db63c_3.png)

Surn off bound， like we would。Earlier， we said exciseise。啊啊。Independent。

Random variables RV as always stands for random variables taking on values in 01。

Independent bounded random of variables。S is the sum of the Xs。 Let's say there are n of these tag。

 It doesn't really matter。Expectation of X。Is new why。Expectation of S is the sum of newwise。

有一 거거든요거든요。And then we set the probability that s is bigger than new plusus lambda。

Is less than equal to sum。Expression like this。Minus lambda squared over2 new plus lambda。

 And there was some lower lower tail as well。 I'll just write it down once more as suggest equal to minus lambda。

Is less than8 of x。M lambda squareオ。Some of the Lord tale never gets into respect in the sense that we never do the proofs of this election that's okay you can do it yourself what I will do is I will very quickly do the proof once because you should see the proof at least once。

😊，And。Because you， chances that you'll have to prove it yourself and if you have to prove it yourself。

Then you better know how to do it。Yes， thank you。好的。That's exactly right。Okay。

And there are various extensions of this， this is basically the tip of the iceberg。

 but let me start with this。😊，Let me just do the proof one。A little bit of algebra， but。

Let me just do this。Okay， so the proof of this。This says， well。

 I want the probability that x is bigger than some bound B。Okay。😊，This is equal to。

The probability that equals the Tx。Is bigger than E to the T。B。呃，放。

As long as Steve bigger than there。E to the Tx is a monotone function。

So I can apply a monitorton function to do this， and I can。T strictly grim。Good。

And now Ill apply Marovs inequality， which is expectation of e with Tx。😊，오前いだ。Yeah。This， by the way。

Is the moment generating function。Of the available lens。

And often this is called the Laplace transform， though I hardly ever use the terminology。😊，Good。

And now， you know， basically we are just following our nose in some sense， we use the fact that oh。

 so in my case x was really s。😊，S is the sum of random variables。So this is equal to E to the。

Sumation or t time summation X。Over to the DB。But now I can use the fact that the xs are independent。

So e to the Txs are independent。So this is just the product。Of the expectation。Of you do the DXI。

Over预柜。So far so。哦。不起。Yeah。Okay。Let me make my life slightly easier。Theyking it assume。

That X size Acon values。In01， not the continuous。Interval。Make my life slightly easier。

So let's look at just the expectation of E to the Txi I。What is this？So。

 if Xi takes on values in 0 or 1。And its expectation is new。

Then the probability of being one equals me I。Okay。

And with probably one minus mu Y you're sitting at zoo。

So this is just 1 minus mu i times e to the t0， which is 1。Plus mean y times e to the t times 1。

 which is E。对对。Okay。Good。So， this is equal to。Broer off。1 minus。M y plus me y。你比个电。Over一的。O。あ。嗯。

What next？What can I do。Still a mess。 there are all these mu eyes floating around。

What should I do next to the product sitting out？好。我在。Take logarithms。

 I could take logarithms in just one minute。 but let me do the follow。Let me。

Apply the arithmetic mean geometry meaning。Okay。But this is umost， you know what MGM is， right？

The geometric mean is at mostly athmetic。So this is the geometric mean to the end its power。

So let's take the arithmetic mean of this thing。 what is the arithmetic mean of this thing。

Why minus us？没有。And。Lets new over and。你对的。え。The end of hour。你来没。Okay。嗯。

Let me introduce some notation I'm you know doing it slightly different from the lectures。

 but thats that's okay every time you do it you will do it slightly differently because you see a different way of doing doesn't matter let me call。

😊，This quantity。O。可以。I need a name。I mean， this is like the average bias of each of these rhino there。

😊，M was the sum of the mu eyes。 So this is like the average bias。 I'm thinking of it as peak。哎。

So this is z equal。And let me just rewrite this。As you said， I'm taking logarithms。嗯。1。And dims。

1 minus P。그 be 이 두。Mus D。本人呢。Nothing really has happened so。没有か。啊。Lg， oh yeah。 yeah。 You're right。

 There should be a log sitting out here。A v equal little x。哦。And times。No。Oh。Okay。😊，O。啊。Yeah。

You need to simplify this okay， so by the way。AndAt this point。

What are the expression what are the objects remaining？There's a bunch of logs and there's N。

There's P， which is really like mu divided by n。There's be。And this tea。

Everything except T is like a first class object。 It's like an object that appears somewhere out there。

Tea is something I don't， you know， tea is something I pulled out of my hand。

So what I should do is I should find。The expression I should minimize。哦。可的。AndNow。

 this is really a problem in algebra。And means of calculations。

There's no more kind of smarts to be done。Actually， there's a couple of smarts that can be done。

 You can simplify your life by using little tricks。😊，嗯。So I can show you how it's done， but the rest。

 you know， if you， if you the rest of it， you zone out， you're like， dude what what's the guy doing。

 I'm just doing that。😊，So maybe I will show you how the rest of the proof goes， but。It's just。

 I know some tricks that I've done before， so I can promote。Yeah。Even so， I mean， of course see。

1 plus x is less。do you so basically at this point I can do whatever I want So before I start minimizing over t greater and equal to0 I can man this in whichever way I want and thats exactly what I'm going to do so so let me actually。

😊，Yeah， so let's use that trick。So well this is like the dirty part of the board we'll do random crap up here。

哎。So what do I want to do？I want to minimize this expression。

So let me just rewrite this thing as n times log of4。So the trick that you said， log of one。Plus x。

 So remember。This is our standard trick， right。Log of one plus x。Is less than equal。

So I could just use that thing。And I could say log of1 plus the remaining。So this。I would say， okay。

 this is stop。Make you say star， actually， you know what？Let me， in fact。sll。This expression。

I don't want to keep writing E XP。Just take the exponent。So what star star is at most？呃。

Help me out this。Times。He。BE这个D。Mピ。Minus T things。哦。Its okay。啊。

How so I want to make this as small as possible， so I should lets say let's take derivative in fact。

 let me pull the P out。So this is， if I take derivatives。Dvising。

Now we get P times N times E to the B。Is equal to B。So， T is equal to。B divided by Pn。Log E to the T。

ok。Oh， things seem to be not too bad。Why。What if B。没别 land。I just fixed the bound， right。

 That's the bound。What's BN？So this is just saying set two to the log of one class lambda over near。

So now I need to substitute this backend。And this is equal PN is conveniently mu。Into the tea。

Is new plus lambmbda over new。-1。Minus。B。Love。Be over new。

 I have this exasperating habit of moving between， you know。

 I just move from B to mu and now move back from U to B， but you'll forgive me my transgressions。ok。

细。个。简 now按m关注。As I said， this is the dirty part of the board， we won't look at this closely later on。

😊，This guy is。Ne plusus lambda over mu minus mu over mu。 So that's lambda over mu。

 that's that's lambda。 the other mu minus B times log of B。好明。哎。And now。O。

So this is already giving you an upper bound， and I can write this upper bound out here。😊。

So let me just write this up。As。This is at most E to the。Lambda。Divided by。Mil plus。

new plus lambmbda。住的。对。M plus line over me。人民 plus。I think this is a month。Because I up bomb。

How do you make sense of it， I this related to that bound。Maybe， maybe not。ok。And now。

 I'll use another。Trick。It says， maybe I'll write it here。诶四。嗯。ok。

So this long term is slightly annoying。I moved from。

Like I use the fact that one plus x is less than e to the x。 I want the other side now。

 So what I'm going to use is I'm going to use the fact that log of one plus x。Is。

Great than equal to x over1 minus。또 lets say。Another one of these， you know。You play with this thing。

So you're going to say。对。You don't want to see me do this。If you， if you believe me。

Just using that analysis you're going to get。M。こ。Yes。できるんです。This last， it's not important。Oh。嗯。

What did we do。Be used。The same kind of transformation idea that we use for shabi chef。😊。

He said for Cheby Cheev， we took the random of variable。😊，And we， you know， squared it more or less。

Here we are using the exponential。 It's growing much faster。嗯。

But we want to make sure that you know it gives us the best bound possible。

 So what we did was once we went there。😊，We used independence to break up x into sum。You know。

 sum of the ss into the product of the x's。And then after that， we just did， you know， we just said。

 look， dude。We have all the information。 We've captured all the information we could。

Into this expression。And then it's just a question of how the brick man play。AndThat's all we did。

So whenever you have you'll be asked to prove one of these bounds， these concentration bounds。

 chances that you'll do exactly the same。And I can you know tell you a little story which is that you know I was in grad school just like you guys and we were trying to understand this dimension reduction phenomenon and there was some。

 some crazy calculation and you know people were using you know whatever。😊，And you know， we sat down。

 we said， okay， you know， what is this， This is a turn of bound And thankfully。

 we had just learned turn of bound in our classes。😊，So we say， okay， we know how to do a turn of on。

 let's just do this carefully。And that came， that became my first piece of book came up there。

So I'm very fond of this calculation。 That's why I issue it。😊。

Chances are you meet it in dark ca and you'll be like， do， I know how to do this。😊。

That's an important part。The important part you know is not any of these particular steps that I took apart from the fact that you know the sort of most important inequality ever one plus x is less than e to the x that is just rephrasing of that。

😊，And the fact that as you can use inequalities going in the other direction as long as you you know。

 you take into account。😊，The fact that。Yeah， the approximation gets worse when x becomes large。Yeah。

The lower chain proved exactly the same。嗯。Slightly different approximations， but morally exactly。

I should put the derivation in the notes。😊，I get lazy。关性。好。佢只你。还だか。嗯哼。Like， ideally， you use and。

 you definitely can。Myow。No， no， no， I think it's the right direction。

I think its So so basically what you are going to do is you will show that by pushing mass。😊。

You could have an arbitrary distribution。By just making it whatever the mean is。

 by just making it a random variable which is0 with1 minus the mean and one with the mean value。

 you can show that this inequality instead of being equalality is inequal。So you can extend it to。

First example。That moves that theorem precisely。Second extension。Sometimes。

Your rh variables might not be independent。But。What you might be able to do is you might be able to say。

 oh， you know， the expectation of the product is at most the product of the expectations。😊。

For instance， there is a class of random variables called。Negatively， I mean。

 there are a class of distributions called negatively associated。

So this this whole area has many different。😊，AndDifferent kinds of distributions for which you can apply this in。

And very often people say， oh， these variables are negatively correlated more or less。😊。

One has to be careful what negatively correlated means。😊，But for instance。

 imagine the following thing。That， Im choosing。어。Enmb big vectors。

Sa that exactly care of them at once。So， I pick a random subset of size k。

 those are ones and everybody else is there。😊，These guys are not independent。

 the fact that the first big factor is 0 tells you it is slightly more likely with the second one is going to be a 1。

 slightly more than k over。😊，对。But you can show that they are negatively associated。

So you can apply the same inequality。For the。For these， also， I think。Yeah。

 various different distributions。 You can show negative association。对的。Heres， here's the crazy one。

 I pick a， I take a graph and I pick a uniformly random spanning tree from this graph。😊。

The variables correspond to the edges。😊，And zeros in once captured whether the edge is not there or there。

Zero is not very one。Interesting， negatively associated。Any problem sense。I'm sorry。

s So basically I'm saying this edge。This distribution satisfies the negative association property。😊。

Which means you can。No， no， no， it's saying there's a。This is an inequality。

This edge being being present or absent from a tree is affecting the other edges in you know crazy ways。

 but this inequality is true。😊，if the tree was like settle was very just like and1 I think are independent objects Oh。

 absolutely， independent objects are definitely negatively associated with that's like。我有关事。Yes。😊。

Yeah， I mean， it need not， its not it's not necessary that it's strictly less than it's less than equal。

 So equality is also possible Independence is negative ES。Yeah。没高额。就是说。No。

 so there's a definition for this。 and maybe in the next homework， there' will be a problem one。

 or at least an exercise。😊，On showing things are negatively associated。第个。I'm sorry。You。

Negative association， No， I think you're looking at kind of sort of the entire distribution。

还有 moment问厕。啊。Yeah， good。啊。There are other extensions which depend on So okay good。

So let's look at these things。We were talking about independence。Independence。

 you can relax slightly， so we talked about negative association。

 So maybe Ill just write down things。😊，We don't have time to go sort of get into all this right now maybe homeworks maybe a future lecture I receive might of you guys have a request on what you would like to see towards the end of the course I'm happy to listen I got a request for talking about Martinale concentration so。

😊，Negative association。Or other forms of negative code。There are variants of things。

There are objectss called Martin。Yes。Yeah。Oh。Well this would。So。You can talk about so so Martinale。

 lets a different sequence is you know， you have a variable x0， you have a sequence of variables Xp。

😊，And this is a Martiningale different sequence if expectation of Xi。😊，Given Xi minus1。Is equal to。啊。

Okay， what am I saying？上声。Let's say。나。So I'm defining this is a maringale different sequence basically each X can depend on the past。

😊，So they are not independent in that sense， but the expectation。

 So these are all0 zero mean rhino variables let say。And I want to make sure that each of these。

So condition on the past， let us say is0， I could ask the question what is the probability。😊。

That theres some。Deviiates from its mean which is0， So it's bigger than some lambda， let's say。

And let's say that these excs are in negative one to one。They are bounded random of variables。

They are no longer independent， but they are conditionally independent in the sense that the I guy you know。

 if you condition on the I minus1， the first I minus1 guy is the I sky is。😊，Have expectations here。

And now you can offer what is the probability that it deviates too much from its mean and mean of the sum is 0。

 right because each of these guys are 0。😊，And a famous inequality known as Azuma's inequality says that it's at most Lada squared over something like。

😊，I might be getting the constant slightly wrong。嗯。

So what can happen is this is kind of capturing the fact that XI could encode information about the first time minus1 decisions that have happened。

😊，So， for instance。啊。You could have， let's say， the following kind of random walk。

 you start off at the origin。And there is。There's minus k。And plus L。At each point in time。

 you go left with probability one half， right with probability one half。

Should I say an expectation of XI given the previous is？Is X minus1， do I need that？

I wanted to capture the differences。嗯。Oh， is that the X variables themselvess。Yes， yes。Yeah。

 that's why I'm looking at the sum of the exercise。We good。对。Yeah。

So this is technically known as Martiningale。😊，Difference。C公司。O。I start off from the origin。

 I am taking a rhino ball， 50，50。😊，But。If I win， so this is， you know。

 I have gone to one of those sort of things that don't exist in nature， a fair casino。

Every time I put down money， I either get a buck more or a buck less。😊，If I win L box， I go home。

 That's my target。 If I lose Kbox， my pocket is empty， I go home。

I want to understand the behavior of this object。Now， notice that once I get you know。

 at each point in time， it is 50， 50 plus1 plus 1 or minus1。

 but if I get to this point from this point onwards all be x are zeros。😊，Because my game stops。

At this point， also my game stops。So your randomy variables are not independent， because if I got。

You know， L wins after that， the next line of variable is definitely going to be there。😊，It's fixed。

However。This kind of concentration bound still holds。没。

So it's true for Nightingales and there are various extensions， you know。😊，Let me not。嗯。

Let me not not spend too much more time on this thing Ive put links on the web page to various surveys on concentration and these are their entire books on this subject so if you are interested have a look。

😊，Or come and talk to me， I can recommend things to read。Good。啊，怪死。对。So， let me。O。So at this point。

 let me tell you a slightly different way of packaging what we just did。😊。

Which will save us some amount of effort going forward。So， maybe。This isn't the best user of space。

 but let me use this。Yeah。So whenever we start off our turn point。

 we always use the Laplace transform， we use macrocoovs inequality。😊。

We use independence or negative association。And we reached here。嗯。

Now lets look at and let's just look at the IID case to make my life slightly easier。😊。

The place where all the eggs are the same。Same distribution。So let me define。The log。

Moment generating function。 Remember， we said this is the moment generating function of X。

Let me define the log room in generating function。Psi of T is the expectation of T to the T。remember。

 these Xs are IID， so that's why I don't have any subscripts on the file。😊，You can get away from I。

 but it makes my life easier right。Okay。哎呀哦， there's a log together。Love moment in reading。

That was the MF。So let's look at this。哦这。That object。 and maybe I'll call it。Bagger。你你过로。X of。是。

AndDFs are identical。The end of them。W。And times。三啲。-2。Okay。Let me just rewrite this text。Minus。哦。嗯。

Or any。屌会 and。B妈。Yeah。And let me introduce an object which will be maybe useful later on。

 depending on how we。Dfinine these things。 So I've already defined one object through log MG。

I'm going to define another object。hich is known as the。I never know which name to use。

 I recall this the。嗯。is fancy names for things。That are very simple at some level， but also very。

 very commonly used。 So I want to tell you。The dual of this object。It what在。Stop。哦。Why let's say。

Ifs the。Nax。Overall。Of D times y minussi。This is it's a definition。This is a function of Y。

It maximized overall， let's say。P greater than equal0 in this case。Ofピ y minus s。Yeah。

Let's look back to what we wanted to do。 We wanted to take this object。And drive it into the ground。

 We wanted to make this as small as possible。So in particular。

 we wanted to take this object and make this as large as possible because there is a negative science sitting our。

😊，We want to maximize overall possibilities of this object。So。Thisこ。Is less than equal to。

Minus n times。What。在 star。哦。你这一点。对。Yeah。This， I call the genetic churn of power。

So if you want n copies of a distribution。If you are looking at the sum of independent copies of a random variable。

😊，What you can do is you can look at its log in here， look at its dual。😊。

And now your upper bound is given by this。And in some sense。

 what we have done is we have just done some packaging。And this repackaging allows you to， you know。

Argue about various different properties without having to work all these things out by yourself。😊。

So， for instance， you can take your favorite distribution， so for instance， here let me mention。

But no is， right。So what is the log MJf of Bnoli。Log off1 minus P。Plus three liquid。We just did it。

 right？This is。The log。我不。And now what you can do is you can go and look up on Wikipedia what its dual is going to be。

😊，And it will tell you the。Is。嗯。The following on。 Okay， maybe I should， I should do this on。

It's a little magical， but it's， you know， it's just。😊，Sas you a whole bunch of algebra。

 So I just wanted to。呃，现的事情。So if psi is equal to1 minus p plus p times c equal the p。😊，哦 no。で在。

Then size stuff。Of why。Is going to be。喂。long。Y over P。Plus 1 minus y。来慢慢话。快。Some else you know。

 I saved you some else。Have anybody seen this object before？This is often known。

As the kl divergence of the cross entropy， cross entropy。Yeah게 divversion。Between why。And别。

If you haven't it doesn't really matter right I mean it is just some well known object thats for all I want to point out that once you use this machinery you can start you know plugging into objects that are already studied this this is a well known notion of distance between distributions。

😊，It's known as the coolback liber divergence。 I don't know whether it's not libbl or Lib blur。But。

Yeah。So。So what is this saying？So I want to say that the sum。好。this is just。Hence。

From what we just did， you can show that the probability that a binomial and P。

If bigger than let's say， n times  Q。I at most。X of minus。And dis。F startup of B over there。

 the X KL。Between two。You can quickly derive bonds。Using just just this formulaism。Sometimes。

 it's less。Transparent， but thats that's not you know。

 one can spend time on transparency and one can spend time optimizing。W。売れなです。

Just wanted to throw this one out and let's take her。2 minute break after this。

 and then I'll talk a little bit。 maybe for the for the rest of the 20 minutes that we have。

 let me at least start off telling you a little bit about。So the next thing that we will do。

 which is that we will try to use just a turn of bound。

In order to show one of the very useful tricks that come up again again in algorithm design。

 which is。Dmen reduction。Actually， there is two places where I feel like turn points come again and again one is specific。

😊，So given a graph， I want to get a sparsel graph， which has the same kind of properties as large graph。

And this is a homochrome that you will see next time。

 which is suppose I take the graph and I sample every edge with some probability。😊。

Does it maintain the same cut？We willll see this in one of the homework problems today。

 I'll let me at least start telling you about。This other。Theorem due to Johnson and Lyden stuffs。

 actually。 Okay， so so I'll talk about dimension reduction。诶。So what's the main idea？So essentially。

 the idea in my mind is the following。The boy they ask you。I want you to give me endpoints。

Which are all at unit distancecing each other。How many dimensions do you need？Euclidean space。

 or I should apply。Npoint， Euclidean space。Youre distance from each other。It's like a simplex。

 three points at equal distance from each other。上一个。Cll points。过来。Setertrahedron。

 it's a simplex n minus1 dimensions， right。对。But suppose I tell you。

That I want you to give me points such that the distance between X and Xj。There are， let's say。

 endpoints。And I want that the distance between X I and Xj lies in。One plus minus epsilon。Now。

 how many dimensions do you have？How many points can you put in d dimensional space such that how many vectors can you pack in D dimensional space so that they are almost orthogonal to each other？

I'm not asking you to be exactly or。Great message。See， it's not really a mystery。So for instance。

 you can show the following。So you can get D dimensions， let's say。And again， exercise。See this。You跟。

You can take。You know so D dimensional plus minus1 to big D。Take vectors， sample vectors from。Okay。

Say the vectors are V1， V2。앞두비。No， some number of vector res。By the way。

 any two vectors you choose from here。Theres two independent vectors you are choosing from this space。

What's their inner product expected to be？The expectation is there， in fact。没有。

The expectation of v1 and V2， the inner product between men and 0。

And it should be concentrated because the fortune of bound。Of course， this needs proof。

And what you can show is that in D dimensions， you can pick n。Which is something like2 to the。

Epsilon squared D， Theres some constant sitting out there。Nectctorors。So so choose so many vectors。

Independently， you can show。That， with high probability。The inner product between X I and X J。

The absolute value of that is that most epsilon for one time。嗯。

You can choose an exponential number of vectors which are almost orthogonal to。行。Oh， these are all。

 you know， vectors of the same land， square root B。Thank like。And so actually。

 there should be appson times。Well it's quite little。Apsilon density me。Maybeviation。那个人。いち。

Im choosing vectors。 Ive renormalized so that each of these vectors has unit length。😊。

This is exactly the reization。 And I'm saying I'm taking random vectors。

 and I can pick so many random vectors in just a union bound。 Turn bound union bound。😊，Uplex。

Can show that all these guys are merely orthogonal to each other。Okay。So if I have n。

 which is 2 to the epsilon squared D， Im saying D is something like。Log n over excellence。Aric。So。

What's the point？I can choose n vectors in so many dimensions which are nearly ortho augmental each。

Not quite orthogonal， but a little more breathing room didn't hurt。 I mean。

 it helped me a huge amount。Yeah。And really， this is the phenomenon at the heart of dimension。😊。

So let me give you the tail， which is vehicles。These two functional analysts， Bill Johnson。

And you're on Linden Straus。In 1984。It will the following fact。It， it's some le in that paper that。嗯。

S。你。Next one。2 after XN。The any points。And。三。New dimensions in space。 I don't know。

 I don't care how many dimensions there are。The endpoint。嗯。Then there exists a map。Yes。

Taking on capital。啊 okay。Such that。F of x， minus f of y。2 norm square2 norm， let's say。

x minus y and the two norm。Is between one minus epsilon。Plus Epsilon。F X， Y， belonging to S。So far。

 this is a trivial statement k could be equal to capital D。😊，嗯。K is equal to log and c。

K vehicle equal equal to bigger log again。I should have said。Epsilon， let's say less than one。

There this two。Yes to get things。变动。You give me any set of endpoints？

I can find an embedding of these points into log n dimensional space。

Such that their distances don't change by more than。1%。喂。

Any set of endpoints I don't care how many dimensions they were in of course if they were in very few dimensions then F should be the identity map。

 but if they are in many dimensions then this is a non trivial theorem。😊，这交。I'm sorry。No， that does。

Oh， that's， that's sort of a next statement。 This is， this is just。So far， this is existence。 Also。

 I'll tell you what the matter like two。😊，Well， thank you。Today， I will not go over time。We in fact。

 show you the thing without going on。I can， you know， add on stuff to this thing。

I can say not only can I find this map then can。Efficient题。fin。ですね。嗯。对。

So let me let me cut to the chair and tell me what tell you all this matter。Is the tanem clear？

So here's， here's the。So you know。There's going to be two features of this thing。

And these are features these are not necessarily required by the theorem。

 but these happen to be features firstly it is going to be a linear map。😊。

So f of Cx for the vector x is equal to C times。You cant be a linear map。Secondly。

It's going to be an obli。What do I mean I won't even look at the data Ill come up with a map that with high probability will succeed Its a randomized term。

😊，So， basically， give。F， such that。开。AnyS。F is good。For this。没太 problem。对。对对。I'm sorry。你们认知道自己。H。

Okay， so， you know， in my mind。Romness is still you know， within the bound of efficiency。

 If you want to determin map， I can also do that。 But you know， then I have to look at the。😊。

Sor of data site。 otherwise， there doesn't exist a single。So maybe还 should。呃 random。我这。

So let me actually give you the， let me。So let me give you the construct。

The construction support yeah。就是。哦。Yeah， so let me let me give you the entire thing and then we'll prove it later on if we feel like。

😊，So here's， here's the map。是。I want to give it there。So here's what I'm want。

Let's pick a matrix here。M is a matrix。 It's its。Fact matrix， its called D dimensions。

 and we always imagining D is much bigger than k。😊，It's a short matrix。M times6。So F of X。

Is going to be m times x。And just for rescaling purposes。

 I'm going to have a one over square decayK or something like。😊，还是么考虑。

This is going to be my my matrix， my my map。M， oh by the way， this is clearly a linear man。

And what are the entries of them？I I D， Norman。0ロ oneだ。在这。AndMy claim is。B F effects。Has。

This property， this distance preserv property。Ass property。Star。With probability 1 minus1 over。不。嗯。

So， in fact。啊。I'm going the prove。我哋个。This注。你什么人这样。Which is like。FB。As。你有。Then。我 any。In for any。

Y next Lexter。X。The length of Apple X。我们原来than。This is the unit vectors。 So the length of x is one。

And one plus epsilon。Maybe I'll put a square there just so that Ill make my legs slightly easier。嗯。

The probability of this happening。Is at least one minus delta。If。嘅。His log。One over data。我 that。

There's one over Delta， let me just。1，0 let n。就图了。有。啊。哎。I'm saying。Here the construction。

Pick any unit vector。Its distance is preserved。With high probability。As long as K is large enough。

 same， same， same behavior。It's a linear map。So， here is what I can do。Now。I can apply。F。I can apply。

Distributional J。To the unit vectors。X I minus X J。Divided by the length of X minus。

It will maintain the distance between Xi and Xj because it will maintain the length of this guy。😊。

发到嚟。And choose two possible highjas。Is going to maintain the distance between all of them。

The failure probability。I at most。And choose two times1 over n。So basically。

 all I want to do is I wanted to show that if I fix any unit vector out here。😊。

Over the randomness of these choices。This map。Is going to maintain the length of。对你长。What。

So far so good。So the proof will require a little bit of work with not too much work。So。

 let me give you the。To important ingredients。对。So let's look at what's happening。

I need to figure out what m times x is right。M is is a matrix where every entry is an independent Oh。

 so I'll call this Gaussian from。😊，That's what everybody calls。It's the。就。M times x。

 let's just look at just the out output of m times x， this first entry。I what。

Is the inner product of this vector with this。So， the first entry is。X1。Time a Gaussian。Plus。

 you know， whatever， it's a sum over I of X times a Gaussian。Independent gossip。

Now I can use the fact that if I sum up two Gaussians which are independent， I get another Gaussian。

😊，So here are facts， right。C times。A Gaussian like this， actually。C times me。Sigma squared。

Is equal to a Gaussian whose mean is。睡秒。Whose variance is？Theres big marmings in the back。Okay。

M sigma quick plus Gaussian。M prime。Stigma of new。 That's a new prime Sigma prime。Squared。

I equal to independent of。What's the new thing？New one plus mean 2 O， new plus new prime。

Sigma squared plus sigma。V to died up， right？Independent right number。对。对。

So what's the outcome of this guy？Xi times the Gaussian becomes normal with mean 0。Vance。Xi squared。

Some of these X squareds just becomes a Gaussian， maybe I should say， you know。

 I shouldn say equal these are distributed the same as。That's what I'm saying right。

This is distributed the same as0 sumation Xi squared。Which is also known as。You back。行。

This entry is the Gaulussci。This is another Gaussian。 This is another Gaussian。

This lecture has key independent Gaussian sitting in there。😊，You are dividing by square root k。

You're taking the song。Of independent governance。So what's the length。Squared of this object。

Thisd plus this squared plus this squared。Divide by K。Because， you know， there's a case sitting on。

A bunch of squares of Gaussians。And youre taking the average of that。Why are you taking the average。

You want to get concentration。And here is because I promised I'd end on time。 And， of course。

 I'm one minute over already。What's the Gaussian look like， I'm going start waving my hands。

 By the way。 This is the point at which I start waving my hands。 What's the Gaussian look like。This。

 right。Well， you know what is this， The tails are very thin。😊，So this is the same as。对。Li were的。

You know， what's the variance of this Gaussian， uniquely。So after a couple of standard deviations。

 theres almost no mass in there。😊，So this we should just think of as you know。

 the purple of standard deviations， like 01。😊，It's a bunch of random variables which are kind of bounded pretty much morally。

😊，How many copies should you take to get concentration Lo many copies？Right。

You need a formula instance， you can formula。And we will do it next。But I should stop before。

Complete travesty， which and I say， oh， I finished that。Anyways， that's the main idea。

 You know the construction， You know the main lemmas。Just proving it。 we just need to prove。

The last statement， and it will take10 months。So I good。Other questions。Yeah。Okay。

 I'll see you guys on Wednesday。