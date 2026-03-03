# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P5：-05-Advanced Algorithms (COMPSCI 224), Lecture 5.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

![](img/33044fe5aadec959938b6c85f0c2a4fc_0.png)

Okay， so I think I'll just get started。嗯。I realized today that I you know I meant to put a final fake problem at the end of the Pet。

 which is just like how many hours did you spend on the Pet because I wanted to monitor that information So I might just set up a piazza poll for that and from PSet2 onward。

 it'll be there。嗯。So Albert Wu， who's Albert Wu， you， okay， so you're cribing。嗯。

Good so today the plan is。Finish the proof of cuckoo hashing。

 I'll tell you one more thing about load balancing， and then we'll move into Fibonacci heaps。

 which is another topic。 So we're going to be done no more hashing。 after today after midway today。

Okay， so cuckoo hashing。 remember that's something we talked about last time I kind of stated。

How it works， we used it to construct Bre filters for the orbit for retrieval problems。

But we didn't actually analyze cuckoo hashing。Okay。Remember， we have an array。

Our hash table of A of size， linear and n。And we have two random hash functions， GNH。From。

And what we do is when we get an item X that we want to insert。We。

Try to insert it in the GXith position。And if it's free， we put it there， if it's not free。

 we still put it there， but then we kick out whoever was there and move them to their other hash location。

Okay， so whoever was there？Was there either because of G or H？So if they were there because of G。

 we'll kick them out and put them in their H location。 if they were there because of H。

 we'll kick them out and put them in their G location。

And then when we put them in their new location， this might continue because that might also be non empty。

Okay。我 good。嗯。And。If this goes on。If the sequence of item moves。It goes on。For at least。

Some big constant C times log n steps。C is something that will come out of the analysis。

 but think of C as 10 or something。See log n steps。We give up。And。We give up， we pick。New G and H。

And we rebuild。The entire data structure。We allocate a brand new array A。

 we reinsert everything from scratch。And if any of these inserts， again。

 takes more than C log n during that rebuilding phase， we again。

Destroy everything and rebuild it again from scratch until it finally works。Okay。

 so the point will be that。This rebuilding will succeed with good probability。

 so in expectation we won't have to rebuild that often。Okay。Good。

So now for the analysis of the claim。Is that。The the expectation of the time to insert。

Is oh of is a constant。Okay。Okay。So let me draw a couple of pictures for what might happen。

When we try to insert things into。The hash table。 First。

 I want to remind ourselves what this cuckoo graph is。 It's something I defined last time。

 So cuckoo graph。So。We're going to first draw a picture whooo graph。This graph has M vertices。

Weanper。So。Of a。And it also has n edges。For each X。We connect。G of x to H of x。

And as someone pointed out last time， this graph could have。Multi edges， it could have self loops。

Okay， so what happens when you try to do an insert？Let's say we try to insert some。X。It could happen。

That。So this value x comes in。That's G of x。And an item ready lives there。

And then we have to kick it out。And something already lives there， and we have to kick it out。

And something there me to kick it out。And then we're dead。So that's one possibility， the cases。

So this looks like this is a path。Right。Another thing could happen， which is that we have a cycle。

So here。Could you draw a picture。X comes in。It kicks someone out。Kick someone out。Kick someone out。

And then。We have a single cycle， maybe now at。It goes like this。Okay， so now。

X7 wants to go back into where X4 moved， so just so that we're all on the same page with how the algorithm works。

What will happen now？X4 will go back exactly。 So now x4 will go back。

And then that's going where x3 was。 So x3 now has to go back。And x2 now has to go back。Okay。

 and then now it happens。Sorry。Yeah， so that was G of x， now we push x into H of x。So now。

X tries to go here。That might kick someone out。Exit。And then maybe now we're dead。So in this case。

Let me draw some boundaries here。So this case here is we have a single cycle。

Let me give myself some more room for the next one。Okay。

And then there's one more case that I want to draw。Which looks a lot like this case。

 but more problematic。 So now， so this is an O case， right。

 just because there's a cycle in this graph doesn't mean we're in trouble。But now。

 suppose this happens， X comes in。It goes somewhere， it goes somewhere， cycles around。Comes back。

Exco somewhere。It around。Go somewhere。And then now cycles back again。Okay。Now。

 this is actually a problem。This would go on forever。So。嗯。Two cycles。This would go on forever。

Justine Harris。Of course， we'll catch this。 I mean， we won't。 We won't。

 might We're not paying attention to whether or not we have cycles。

 but we're not going to go on forever just because we have this。

We have this here which says that if we go on for more than login steps， we'll just give up。



![](img/33044fe5aadec959938b6c85f0c2a4fc_2.png)

That could happen because of a long path， but it could also happen if we end up in this kind of infinite loop。

Okay。So we could write。嗯。We could write the time。So let's say time。Runtime is T。To do this insertion。

We could， we could define some more random variables， we could say。We could say that。PI。Or PK。

Is indicator。Random variable。For having。A path。Of length。At least K。Okay。We could say CK。

Is an indicator。RV。For a case2 configuration。Of length。At least K。And then finally， we could say。

Let's like D， let's say D stands for double cycle。Di。Is an indicator random variable？For have for。

having。Two cycle configuration。Yeah。This is， this is， yeah， this is for inserting X。All of these are。

 what do we insert x， what do we see as we insert x？Okay， so we can write。

We can write down that the expected time。Okay。Is。The sum overall K。Well。

 the expectation of the sum overall k。Of PK。Right。Plus， the expectation of the sum overall K of CK。

People agree with me？Plus。Di。For inserting， know T is the time for inserting a single item。Plus。

 and let me write now this plus。Okay， so now if this happens。We will definitely rebuild。Okay。嗯。Plus。

 D times。You know， N T。I'm sorry。Oh。Yeah， so。Plus， the probability of D。Or like yeah。

 probably of D being one。Times。N times the expectation of T。Plus。

The probability that we have to that we go on for more than n steps。 So for log n steps。

 the probability that to go on。For more than login。C log n steps。Times。And expectation team。So。

The way that this is going to work out is basically we want this。And this to be really tiny。

 let's say， like one over n squared。So that when you multiply it by the end。

 it doesn't really matter。So that these will be kind of the dominant things that play role。Okay。So。

So now we need to bound the expectation。 We're gonna to use linear of expectation。

 We need to bound the expectation of P， K， the expectation of C， K。

And the probability equals 1 as well， et cetera。 So let's look at expectation of PK。

 which is just the probability of having a path of length bigger than equal to K。Okay。Okay， so。

What we'll do is we'll look at all possible paths of length bigger than equal to K。And ask。

 what's the problem that we see this particular configuration or this particular occurrence。

 and then will'll union bound over all of them？So。Let's fix。What do I mean by path of length， okay。

 I mean that。The number of edges here is one， two，3， that so here K is3。

 just so that we're all on the same page。So， fix。Fix x2， x 3，2。X K plus1。Okay。Also， let's fix。

Fix all the hash values。There are like k plus1 vertices here。They a fix all of them。Fix assignment。

Of。The K plus 1。Hash values。To the vertices。ok。So we're asking ourselves。

 what's the probability that？We see exactly this configuration。Probability that we see。Exactly。

This path。Oh， and let me also say。嗯。Just to be clear of the way I'm doing this。

There could be more action happening over here， I don't know。There can be more stuff happening。

 I just want to ask if you look at the first case steps， what's the problem that you see this？Yeah。

So every vertex is a hash value。So the fact that you have this path means that h of x2 equals g of x3。

So or the other way around， you know， there's like it could be G in H。So， maybe。So， okay。

 so I'm asking。So when I insert X and I look at what happens in the cuckoo graph。You know。

 I might see some picture that looks like a path of length K。But that path of length K。Could be。

 you know， I don't know which K plus1 vertices are involved。Right。

And I also don't know which K edges are involved。 The K edges meaning which items。

 So for each possibility of those K plus1 hash values and those K items， I I'm gonna ask myself。

 what's the probability that this is what I see。I'll see exactly like these vertices and these edges。

And then I'll union down over all possibilities。So。Wantants a bound。So we have that the number。

Of hash values。Is。I guess M。To the K plus1。So there number ways to pick the vertices。嗯。

And also the number。Of。嗯。Ways to choose edges。Ass。N times n minus-1 times。N minus k plus 1。

 which is at most end of the K。嗯。Oh， wait， before I do that。 So okay。

 the problem that we see exactly this path。1 of all， I guess I' sorry。 I should have said that。

 This is equal to。1 over M。To the K plus1。Times。To to the。K。Okay。And then now I want a union bound。

So I mean， just have curiosity， people， do people see why I said this， First of all。

 do people see why I said there's this2 to the K here。Yeah。Yeah， exactly。Because yeah， exactly。So。

 yeah， so what's the probability that。knowG of x2 is that and H of x2 is that well。

 it's1 over M to the actually that should be 1 over m to the 2K。And then there's a1 over M for x。 So。

 so what' it probability that G of x is that vertex， it's 1 over M。

And then what's the probability that G of x2 is that and H of x2 is that， it's one over m squared。

But could also be the other way around。 It could have been H was that。

 And G was It could this could have been H， and that could have been G， right。

 So there are two choices。 So the probability of seeing exactly this configuration is one over M for X landing there with G times1 over M squared to the K for everybody else。

 times 2 to the K。Okay。And then now we need to union bound over all possible configurations that look like that。

Well。嗯。Well， we need to choose what these actual hash values are。Right。And theyre K+1 vertices。

 so they're m to the K plus1 choices。How about the number of ways to choose the edges。

 Well this's just choosing which items are there。 So that's end the K choices。 So that implies。

By a union bound。The expectation of PK。Is that most。嗯。N to the K times m to the K plus 1。

Times1 over m times 1 over m to the 2 k times 2 to the K。

So this one over M thing here is that's exactly this。So things start to cancel。

This M goes with this M。Here we have one over m to the K。 Here we have n to the K。

 So this is equal to。2 n over M to the K。And this is why I picked M tob4 times n， I believe。

 over there。So this is equal to。One over two to the K。Yeah。Sorry， we're here。Oh oh， I see。 yeah。Yeah。

Okay。Good， so that's that。So this summation is geometric and it's a constant。Okay， so。

Now I want to look at C， so like this kind of configuration here。Actually。

 let me do something more colorful。Okay， so the point here is。

So you could redo the computation basically the same exact way I did it。

But the main observation here， so for CK。There are three types of edges。Right，There's these edges。

 there's these edges， and there's these edges。At least one type。Has。

At least K over three of the edges。So by the path analysis。The expectation of C， K。

Is that most one over two to the K over three？Or something like that。嗯。

Or maybe three over two the K over three by a union bound over the different colors or something。

Is that what I want to say？No， no， no， no， no， just。

So just look at the longest of the three groups and just ask， what's the problem that you see that？

是这。So now。Oh。嗯。So now we want to compute。 So again， this is another geometric series that I yeah。

 so that thing is a geometric series as well。So that's a constant。

 So now probability that d is equal to1。So， for。D。We want to。Probably that D is equal to1。Okay。

 so I always。This is the kind of calculation where if you're off by ones。

 you get a completely wrong answer。So I want to make sure I'm not off by one。Let's see。Okay。

 so I think let me just。So I want to remind myself。If it's a length K tour。

 how many vertices are there？Let's say that。This goes on one，2，3，4，5，6，7，8，9 steps。

 but the number of vertices is1，2，3，4，5，6，7。So the right answer is there are k minus two vertices。

So for a length。嗯。K。Tour of this type。There are。K minus2 vertices。And by K lengthy tour。

 I mean there are K edges。Okay。So。Let D。Be an indicator。Random variable。For length K。For having。

A length。K tour of this type。Which implies that the probability that d is equal to1。

Is at most the sum over all K。Of the expectation of DK。Or the problem that decays one。

This is just a union bound。So we're going to show that。

Our goal is going to be to show that this sumation will be some geometric series that is big O of one over n squared。

Okay。And once we get that， then。This would be one over n times the same thing。

 so it basically doesn't matter。You can move it to the other side and some of the same kind of thing will happen here。

Okay。Okay， so。Again， so let's。Look。At a particular。嗯。Configuration。Of length， okay？Okay。Yeah。I mean。

 so now that I think about it， I mean， I think it's actually equality because they think these are disjoint events。

But。So the point is。DSo D is the probability that we see a picture like this when we try to insert X。

Right where it has。The case step is exactly where you close the second cycle。So。For D to occur。

 you have to have this picture for some K。So I'm just trying every possible， okay。So yeah。

 so I think this is so I mean， this is the same thing as。T want me to be more pedantic， so let's say。

This is the probability that。You know，D1 equals 1 or d2 equals1。Or forever。

And then by the union bound， you can say this is at most the sum of those events。

 but these are actually disjoint events。 So this is equal to the sum over K。

A probability that DK is working。I don't have to that？Does that answer your question？All right。

 so you believe it？Okay。So let's look at a particular configuration of length K。

 What's the probability that we see it？嗯。So we said there were k minus two vertices。Right。

So I think this should be。1 over。嗯。To the。So one over M for where H okay， so actually。

So x goes into here， so we know that this is G of x。And then we know that that's H of x。

So the problem that this is g of x and that's h of x is 1 over m squared。

Then everybody else is connected by two people as well。

Right everybody else is an edge connecting to people。

 So the problem their hash validations go there is what over m squared。To the number of。People。

 which is。K。There are K different items。Times again， this two to the K。Okay， how about the number。

 So now we want a union bound over all configurations。Oh， by the way， before I forget。

 I meant to say this in the very beginning。So I send this email about half TFing。

So if anyone wants to have TF， contact me at the end of this lecture otherwise。

There are probably too many people for one TF to grade。

 so I mentioned the very first lecture that I'll have grading duty。

 so each person will have to do grading duty once in the semester。

So people need to sign up for a grading duty for PSet one， maybe like。Two people。

 so there are three problems， the TF plus two others。Each person takes a problem。 Okay。

 so just like scibing duty is what first come first serve， grading duty is first come first serve。

 So you should sign up early。 Oh， I see laptop coming of it。 So yeah。Okay， great。

 so now we on a union bound， so back to business。So how many different configurations are there of size K that look like this？

So we have to choose what the actual hash values are。It's the choice of the vertices。

So they're at most end of the k minus two of them。We also have to choose。chooseose。嗯。

Let's say where first cycle， where the first cycle starts amongst these case steps。

How long the first cycle is。And then where the second cycle starts。Yeah。Wai sorry， Sa。 Oh。

 actually in wait choice。 it should have been。Okay， if they were in one cycle。あちゃ。You mean here？

Her here。This。So。So I'm just saying。Did I forget， is this off by some factor？

So here I'm looking at the case of two cycles。Andm so like here's my two cycle configuration。

 And'm I have labels on them now。 This is a particular edge， a particular edge， et cea。

 And I'm asking， what's the problem of seeing exactly that。Is that okay， yeah。

 feel free to stop me if I。Say something crazy。Okay， so。So okay。

 so there are these k minus two vertices we can choose who they all are。

 so they're most m to the K minus2 choices。There's also the choice of who the people on the edges are。

Okay。呃。So choice。Of the edges。There's at most end of the K of those。And then。We can also choose。

 so I mentioned we can choose where the first cycle starts， how long it is。

 and where the second cycle starts。Right。Choice。Of。Lengths。And starts of cycles。

So that's at most k cubed。K for each of them。K for the two starts and K for the。

Lth of the first cycle the length of the second cycle is already implied by the fact that this is a length Kour。

But you could throw in another factor of K， it wouldn't really matter。And if I did this correctly。

 which。Oh， yeah， I wish。Yeah， I keep getting。I've been getting off my ones a lot I。

Reason through this to myself then。Hopefully I'm not off by one right now。So， that implies that。

Probability that Dk。Equals1 is at most， so this is a union bound now。Over configurations。Of。

2K plus 2。It seems yeah I I feel like I'm， I'm already being too good。呃。So this is at most。

M to the K minus 2。Times n to the K times k cubed。Times and then that thing。嗯。One over。

M to the 2 k plus 2。Oh no， no。 I think I I'm not I'm not being too good。Okay， good。Times2 to the K。

Okay。So。Remember， M is 4 N。 So these combined give us n to the K。 and this is N to the。

OrN to the 2 k minus-2， I am being too good。How am I doing this to myself？

This is end to the 2 k minus2， and this is end to the 2 k plus 2。

So that should be one over end to the 2 k plus4 to the end of the fourth。And then。

Here we have again2 to the K okay， so that cancels。That's taking care of the ends。 and then we have。

Times K cubed。Times。So that's 4 to the k minus2 times 2 to the K。

Over what's left here is4 to the 2 k plus2。That goes away。诶。And that becomes four to the K。

And this becomes1 over n cubed times k cubed over 2 to the K。Sorry， end of the fourth。So I apologize。

 so I definitely am off by one because this should be n squared。But。Kme minus two vertices。

Why is it K -2？It should became -1。So I counted and then I thought I got k minus-2。

 so let let me just draw this picture。 So this looks like this， this like that goes back。

 go somewhere， go somewhere， go somewhere， go somewhere。 So this has length kaving 1 sorry， kaving 1。

2，3，4，5，6，7，8，9。And the number of vertices is1， two，3，4， five， six， seven。Washy is it nine？1，2，3，4，5。

6，7，8，9。Yeah。So I lost the one somewhere。 and I don't know why I this always happens to me。

 So I sorry I'll fix it in the notes。Otherwise， I'll go crazy finding the one right now。But I mean。

 the point is that you're going to get something that's much less than one over n。

 So this whole thing。This whole thing is now a geometric series that becomes one over polyen。

So this sum k cube over2 to the K converges to a constant。This is left with one overpoen。

 which cancels that n over there。And that becomes insignificant。Okay。And actually。

 we basically already talked about。 We basically already proved that this thing。Is small as well。

Because for this to happen， for us to go from many steps， either D has to occur。

Which we showed happens with small probability。Or。We have to have P log n or C log n occur。Right。

And we said that those PK happens with probability 1 over2 to the K。

So if we pick C log n where C is big enough，1 over two to the C log n will be one over polyan for an arbitrarily small polyan。

So that's basically it。Other than being off by one somewhere。Questions。

While you think of your questions， I'm I'll try to find this off by one，It's very annoying。

You know what I think it is， actually。呃。I think that there aren't actually K items。

So there are nine edges here， but the actual number of items， this would be like x2， x3，4，5，2 again。

And this is the X itself。And then six， seven， eight。So the number of items here is from2 through8。

 which is actually seven items。Not， not k items。 So K minus two items。系。

But let me not promise that because I don't want to go through this and be off by one yet again。

But yeah， okay。I said the length of a tour is the number of edges in the tour。

 like the amount of times you go around， but that's not the same as the number of items。

 I don't know if maybe that's what you were trying to tell me。Okay， anyway。So。Off by one yet again。

So that's pretty much it for cuckoo hashing。And there's just one last thing I want to say about hashing。

 and don't worry you'll see more on PSE2。Before I move on to nonhahing。So。Last thing on hashing。

So I want to show you yet another example where we somehow take advantage of having two hash functions like cuckoo hashing。

But we're going it's going to be something totally different。

 So this is going to be called the power。Of two choices。Okay。And this is the。This is the basic idea。

So。Recall。Hashing。With chaining。So hopefully people remember what that is， we had a hash table。

 we had our N items。And they're hashing into this hash table of length M。

And each element here is actually a pointer to a linked list。

's you some wubly linked list of items that hash to that cell。Some might be empty。

 some might have multiple items。So just to make sure。People remember things。If H。

 if this hash function， H。Is drawn is drawn totally at random， like not K is independent or anything。

 but just a random hash function， perfect random hash function。What's the length of the longest list？

Do people remember？And let's that， let's say that M is equal to N。Yeah， so log n is true。

 it won't be more than log n。But I claim we said something better。But we didn't talk about。

 I don't think we might have said hashing with chaining when I said it。I just said balls and bins。

 If you have n bins and you have n balls and each ball gets thrown into a totally random bin。

How many balls will the heaviest bin have？So， yeah， log in over log login。 Yeah，'s exactly。

 that's right。 is log n。So I mean， it's a little better than log n， but not much better。Okay。

So this was， I guess， maybe two lectures ago。 This is the first lecture when we started hashing。

 I mentioned this。So we mean， we said to that if H is drawn from a two wise independent family。

 the expected query time will be a constant。 I mean， the query time is the length of the list。

 of the linked list， right。So in expectation， it'll be a constant。But in fact， with high probability。

 the worst case will be at most log n over log login。

So it would be nice to have a small expected time as well as a small worst case time。

So here's a simple idea。So let me make sure I drop it。Give it the proper reference。This is。Azar。

Broder。Carlin and up fall。scom 99。So the idea here is。Pick。2。Random hash functions。GNH。

When inserting。X。Place。In the。Least。Loaded。Amongst。A G of x。And。えュ。And when you do a query。

 you'll search both， you'll search both in the G of X location， as well as the H of X location。

So now we're throwing n balls into N bins at random。But when we throw a ball into a bin。

 we actually throw it into two bins and then put it in the smaller of the two bins， okay。

So it seems intuitive that this should do some amount better。

It's not clear how much better this should be。Will it be a constant factor better will it be？

Asymptotically better， I don't know。嗯。So。And he who's seen this before， by the way？

Has anyone seen this？Okay， that's reasonable。So。With high probability。The heaviest bin。Has。At most。

Any guesses？No， constant， yeah， it's a gas node and that's not constant。What？Yes。Lwn。

 La and over La2 plus theta 1。Items。So in fact， it's very tightly concentrated around this number。

 So with high probability， you'll be this number plus or minus a constant。Okay。

So this is what's called the power of two choices。 We， you do exponentially better， right， I mean。

 the difference between log， roughly log n and。Log log n is is exponential， just by。

Just by this simple thing。So what's a natural- I mean， now that I told you that。

 what's a natural thing to ask？Power three choices。 Why don't I hash into。You know， you know。

 D choices。 Why don't I hash into D locationss and then put into the least loaded of de locationsations。

 right， query time will go up by a factor of D。In expectation。But in the worst case。

 we might get better worst case behavior。So power。Of D choices。Any guesses？About what happens there？

I'm sorry。This。Actually， that's exactly what happens。😊，You get lawn， La N over La D。

Which is unfortunate， right？When you went from one choice to two choices。

You went from roughly log to log log。But then when you go from 2 to three choices or2 to D choices。

 you're really only changing the base of the log， right， I mean。

 this overla 2 is just log base2 of this， whereas this overla D is log base D of this。

So you're just changing the base of the log， which is a constant factor。Right。Okay。

 so I'll just mention one thing before we talk about how to analyze this。 So there was。

It was another。Take on power de choicess。I'm just going to state it。

 we're not going to actually prove anything。嗯。So I don't know how to pronounce this name。

 I don't know if anyone speaks German。 I don't know how to pronounce O with an Ulat。

 Does anyone speak German。Fuck。啊。Okay， yeah， okay。I'll not repeat that。So。That's his name。And。

So he he says， do the following。Break up。Bins。Into D groups。Each of size。N over D equals size。

When you insert an item。嗯。Put put check。Random。Locations。In each group。So it's not just going to be。

 you know， it's not just D random locations period。 it's one random location per group。

 which is D locations。And。Break， put and lease loaded。Loaded and。Break ties。So。

 it seems like the more random， the better， you know if there's a tie。Between lease loaded bins。

 I'll put it in a random one of them。But no， break ties by。Plaaccing the leftmost one。

It seems like a weird thing to me to do。And here。You could ask again。

 what's going to be the load of the heaviest bin？It'll be。

So he he proves even the the right constant factor， but I'm not going to bother writing that he gets。

Lwn， lawn， and over D。So basically the base。You can think of D as， I guess。As line of E to the D。

So the base， instead of becoming， instead of the base becoming。D， it becomes E to the D。

 So I don't know why this happens。 Actually。 I didn't actually read that paper。呃。

I just found it very weird。Okay。ok。So questions about。

 so I'm only going to look at power of two choices， I'll show you how you would analyze that thing。

And when you analyze it， know， you have to be rigorous。 So first。

 I'm going to show you the non rigorous argument。Just so you can see where log login might even come from。

 and then I'll say what you can do to make it rigorous。Right。Intuition。For the power of two choices。

Oh， and I should also say。You know， if you want to read more about this， there's a survey that has。

 there's been lots of papers on things with power of。Of multiple choices and various variants。

If you want to see more， there's a survey。By。Well， someone who you might know， Mi and Moer。

And two others。R。And Saraman。So。You can check that out if you want to see more。Okay， so。

So why should this thing happen？B I。Equal the number。Of bins。With load。at least， I。 suppose， I mean。

 of course this's a random number。But let's say that I know for certain that there won't be more than BI bins with load。

 at least I。I mean， I'm in the non rigorous mode here。And。What。The height of x。Be the。Be such that。X。

 wa， so my hash function。Okay。Let me make it capital H because my hash function is supposed to be G and H。

 right， little G and little H。Be such that x is the。H of XF。I am。Inserted。Into that bin。Okay， so。

I want to say something about now what should B i+1 look like？So I know that。DI plus 1。Is that most？

The number of items X。Such that the height of x。Is it at least i+1？Okay。So。Let X I。

 let's let A sub x。's b sub x， let b sub x be an indicator random variable。For event。That。

H of x is at least i plus1。So what has to happen？Remember， this is the non rigorous argument here。

 So x comes along， and then we hash it。And。What has to happen for its height？😡，To be at least i+1。

Well， both of the bins that it hash to have to have height at least I。So the probability that。

H of x is at least i plus1。Is equal to the probability that。呃。H of x。Has load at least I。And。G of x。

Has load at least I。But H and G are independent functions from each other。

So this is equal to- this is at most。呃。BI over N。Squared。Right。So this implies。You know。Ignoring。

 ignoring。The fact that things don't behave exactly like their expectation。This implies that。

If everything。You know， is as。Expected。We have that。BI plus1。Is that most？N times B over n。Squared。

Right。There are N items。😡，For a given item。The expectation of its indicator random variable is this。

So if you sum over all items， the expected number of items that have a high height will be n times this。

And this is the same thing as saying。BI plus1 over n。Is at most。BI over n squared。

So once you're in a situation where。BI over N is less than， let's say， a half。Then。

This fraction of of bins that are。That have。A high load is like decreasing as a power at's squaring each time。

Right。So let's say， for example。We were let's say we knew that， B10。Over n。Was it most a half？

We managed to prove that。Then。You know， beat B sub 10 plus J over N。By this would be at most。嗯。

1 over two to the2 to the J， I guess。And we're done when this number is something less than one。

 That means there are no bins。嗯。So。We're done when。Danwen。Be to the。10 plus J over n。

Is that most one？Applies。Two to the2 to the J。Is bigger than equal to n applies。

J is it bigger than like log log in？Theyre strictly less than one。If it's strictly less than one。

 that means0。W of red。So that's where it comes from。Okay。Do you feel convinced？Okay， but I mean。

 then it's a matter， really， I mean， this is the main idea， in my opinion， right because。

The only thing that's wrong is this。These are random variables。

 You can't just say that this always happens， right， You have to argue that with high probability。

 something good will happen， et cetera， et cetera。 But this is really。The main idea。O。

So now what we're going to do to actually make this a little bit more rigorous。嗯。So。Let's define。

Alpha is sub 6。Is equal to n over 2 e。AndLet's say that， EI。Is the event。That。BI。

Is at most alpha I and in general for larger eyes。How do I want to define find this alpha？嗯。

Alpha I plus 1。Is equal to。E alpha I squared over n。I mean。

 it's almost doing exactly what the fake proof did， right， So here we said that。嗯。

B plus1 is n times B B plus1 is B squared over n here。

 we're just making our upper bounds behave in the same way。

 We give ourselves a little bit of slack because there's this factor of E here。Right。

But the basic idea is going to be to say， look。We just want to show that。Will show that。

With high probability。All events。Yi。呃。Occur。系嘅。Okay， so the first point is that。Probability of E6。

Is equal to one。Because。Basically， n over 2 E。So how many bins could there possibly be with load at least six？

I most enter over six of them。And N over 2 e is bigger than n over 6。嗯。Well， I could have， I mean。

 I could have， I could have started earlier maybe and then said just as long I could start with T。

 And then as long as this thing is bigger than it over T would be a valid。Statement。Yeah， I mean。

 it's just because at some point， we're gonna to use turn off bounds。

 and we want to make sure that things are like small enough to， to argue about。

A union bound kills everything。Yeah， it's。Yeah， it's not that。Great。Okay。嗯。And so。

We're going to have two claims， so claim one。Will be that the probability。That。BI。Plus one。

Is greater equal to alpha i plus 1。Given that EI has succeeded。Are strictly bigger。Will be at most。

Big O， some constant times， the probability。That。If you pick。If you pick a Bnoulli。

 if you pick a binomial distribution。T right like this。Bomial distribution with parameter。

 alpha over n squared。That thing is bigger than alpha equal plus one。系。

Which is basically what the non rigorous proof was doing。What's the proof of that？

So we know that the probability that。嗯。BI plus 1 is greater than alpha I plus1 given EI。

Now we're going to use Bayes rule。Times the probability of EI。Is equal to the probability。

That of B plus one。Bigger than alpha P plus1。Yai。Which is at most。The probability that B plus1。

It's greater than alpha I plus one。Sorry， let me write this again。嗯。Oh okay， so actually。

 this is not how I want to say it。So what did we say before， we had thatt point at B plus1。

Is that most the number of x's？Such that H of x。I's bigger than equal to i+1。So now again。

 we have that。D。😔，This thing。BI plus1。Is that most？嗯。Is that most that same exact thing。

 which is the sum of X？A piece of xs。I use that。 I shouldn't have used the same letter to mean loads of。

那个。So。Actually， I think。I think there's really。呃。What I want to say here。 So okay。

 so certainly now what I've shown， certainly what I've shown is。

The probability that B plus1 is bigger than alpha I plus1 given EI。

Is at most the probability that the sum over Qx' is？嗯。Bigger than alpha P plus1， given an EI。

And I think。诶。I had a proven mind and know it。Yeah sorry， I think something is now bothering me。嗯。

The thinghing is that if you condition on EI， then this is not。

This is not just going to be B over n squared。Okay。

 there's some dependency issue that I need to fix in this proof。嗯。But sorry about this。

 So there's some to fixing this proof。 But if you take this for granted。

 then basically now this is just the turn off bound。Okay。

So what's the probability that a sum of bernoully random variables is bigger than some amount。

 that's a turn off bound and then you union bound over all the levels。

And that's basically how it goes。But there's something that I need to fix here。Sorry。

 I'll have to fix that in the notes。Sorry。Have to fixes the this。So now what's the probability that。

Been of。Alpha I over n。Squared is bigger than alpha plus1。Right。This is the turnoff down。

Then your union bound。Overall， I。And that's basically how it goes。Sorry， so I guess the。

The main tricky thing which now is escaping my mind is exactly this。So yeah。

 I know that might have been。An annoying point。But are there questions about， I guess。

 the structure of the proof besides the proof of that claim？Yeah。Yeah。No。

 you would basically get the same thing as the turnoff bound up to Constance and the exponent。Okay。

Any other questions？I dont know if there are any more questions。

 I guess maybe I'll just tell you at all。嗯。What I'll cover next time。So no more hashing。And two。

 we'll look at。Data structures。And amortize analysis。Look at heaps。So binomial heaps。

As well as Fibonacci heaps。And we'll look at， for example， s trees。

So we'll probably see heaps on Thursday and s trees next week。But I'm just have curiosity who's seen。

 who's seen Fibonacci， Fibonacci heaps。Okay， I mean。

 and who's seen like the analysis of Fibonacci heap and， not just the。The fact they exist。

That was interesting every。So I'm curious， so for people who raise their hand at Harvard。

 did you see it in a Harvard class or was it？Or did you see it elsewhere？おざ。Oh， I see， I see。嗯。And。

As part of the am analysis， we'll see potential function arguments。

So where heaps all about to remember what heaps do， so heaps？We store N items。With keys。

That are comparable。And we support some operations， so we insert an item with a key。

We also decrease key。To some decrease keys from x to some new K， where K is less to go to x。

 let's say。And we also delete min。Which returns the minimum element and also deletes it from the heap。

Okay， and remember Dykstra。Exextras algorithm。Uses a heap in its implementation。

 and its running time。Is。So let's say we have N vertices。And we have images。嗯。

So it'll be M times insert。Plus m times decrease key。Plus n times delete min。Okay。

And if you remember binary heaps， so if you've taken say for example， CS124 and seen binary heaps。

 you know that you can implement all these operations in log end time。So you'll get running time。

 which is like basically M log n。M plus n times log n， but if it's a connected graph。

 then M will be bigger than N。 So M log n。Fminacci Heaps are able to all these to be able to do these operations in constant time and delete min and login time。

 which gives you M plus n login。So you'll get a speed up in。

In shortest paths with non negative edge weightates， and also in all pair shortest paths。

 if you just run diktra n times。Okay。So we'll see if Fibonacci heaps next time。

 And I'm sorry again about this。 I'm going to have to fix this in the notes。嗯。Anyway。这别。

