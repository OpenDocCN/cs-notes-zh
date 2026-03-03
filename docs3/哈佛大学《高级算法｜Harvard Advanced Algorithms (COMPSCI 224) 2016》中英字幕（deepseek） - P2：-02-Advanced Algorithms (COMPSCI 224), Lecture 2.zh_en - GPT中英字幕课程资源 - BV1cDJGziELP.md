# 哈佛大学《高级算法｜Harvard Advanced Algorithms (COMPSCI 224) 2016》中英字幕（deepseek） - P2：-02-Advanced Algorithms (COMPSCI 224), Lecture 2.zh_en - GPT中英字幕课程资源 - BV1cDJGziELP

I guess I'll get started。

![](img/ef71a82020f5e8b6086547d3c889f745_1.png)

So today we're going to do fusion trees， but before I do fusion trees。

 I just wanted to say one thing about。Vanom to Boaz trees， which we did last time。

 So somewhere in there。 So we did venom de Boas trees， and then we did whyfat trees。

 and they got the same bound。The argument， so for venom Du Bos trees。

 I mentioned instead of using arrays， use hash tables。

And then you'll get O of N space instead of O of U space。Okay。It turns out that there is something。

 So it turns out that there's even an exercise in C，LRS。Exercise 20 dash1 part F。

 which says exactly that prove that if you use hash tables instead of arrays， you get linear space。

And what I told you is actually their intended solution。 but it turns out that there's an error。

 There's a very subtle error so the argument that we discussed in class that gets O of M space is not really O of N space。

 It's slightly worse。 And it's not just the argument。 It actually doesn't get O of M space。

 So that's going to be a Pet problem。 I'll tell you exactly which sentence I said that was wrong。

 And you have to tell me why and fix it。 Okay so。But you can get O in space and you'll see that on the Pet。

Okay so。And why fast trees， as I described， actually do get event space with this indirection。Okay。

 any other questions before I start？Yes， okay。Now we'll do fusion trees， so fusion trees。Remember。

 we're solving the predecessor problem。This is due to Fredman and Willard。And I guess 93。嗯。Right。

 and we're going to look at the static predecessor problem。 later after their paper。

 it was made dynamic， so there was a paper by Anderson and Thororrup。

So here we have Anderson Thororrop。And they got。An update time of。

Log based W of N plus log log U or log log n， sorry， updates。And it's deterministic。And then later。

 Ramen。OhAnd are you sccribing today？Got。Logway W of N。Updates。And this is expected。

Expected running time， so it's a randomized algorithm。Okay。in all cases， the query time。

The query time is O of log based W。And then okay。嗯。I'm going to show you just the static version。

 not these two that gets query log based W of N。 And there's going to be some。

Polynomial time amount of pre processing。 It actually won't be that bad， but it'll be。

More than sorting time。To actually create the data structure。

 given the static points in the data structure。So that's why you can't use it for sorting it's something。

We talked about last time。But you could use the dynamic versions for sorting。Okay。

So the basic idea of fusion trees。Or to have instead of binary search trees， to have。

K are research trees where K is。Bigger than two， Okay。

 so we're going to have a fusion tree looks something like this。Okay so。Actually。

 just a show of hands， who here has seen or heard of either two， three， four trees or bee trees。Okay。

 so a large number of people， but not everyone。Okay， so the basic ideas going this follows is。

 let me actually write it a different way。Every node is not going to have one key。

 but it's going to have， say roughly k keys。Okay。AndSo know， we might have。5， 15， 27， 32， and 48。

 these are sorted。And。Hanging off this is going to be a subte of everything that has a key less than five。

Hanging here is going to be another tree of everything between 5 and 15。

 everything between 15 and 27， etcter。And then there's a note here。

 there's another big fat note here， et cetera。And then each one of these branches in many directions as well。

Okay， so that's， that's the basic idea behind。Hes having larger air trees than just binary search trees。

Yeah。So these are sorted。So everything hanging off here is less than five。

Everything hanging off down here is between5 and 15。RightSo right in a binary tree。

 there's just a single key in the node and to the left is bigger to to the left is smaller to the right is bigger。

Okay， so。So we're going to have。This basic structure。With K。Being theta of W to the1 fifth。Heese。

P node。Okay。So。You know， what is， what is the height of this tree？If you have， in general。

 in terms of K， what's the height of this tree。Yeah， log based K of N， right， And that's， you know。

 so we're having。So。That implies the height。Is。Well， it's O log base W to the fifth。Of N。Right。

But if you just remember what your base， your log arithmetic， this is the same thing as。

Log n over one fifth log W。Right， which is just the。L based W of N。 So this is where。

This is why we're hoping to get log basedase W ofN。有谁？But there's， of course， a problem here。

 which is。Our time is not just the depth of the tree。 You know。

 we have to also take into account how much time we spend at each node of the tree， right， so。

Kind of naively， what you might think to do is start to the left and then go see where I am and then go down。

Okay。That will take you k time per node。 So you get K times log base K of N。

 which is always worse than log base2 of n。You can do a binary search。

Then you would get log K times log base K of n， and the log K is canceled and you just get log n again。

Okay， so really， I mean， to really， to make this work really。

 we can only spend a constant amount of time per node。Okay。嗯。Now。

Does anyone see something that's like blatantly？Something I just simply can't work about that。Right。

How are we going to spend so there are w to the 15 keys in here。Okay。

 how much space does each key take？Not not log W， but W。 key， A key fits in a word， right。

 So the amount of space to represent a node is w to the6 fifths。

We can't even fit it in a single machine word， so how can we process it in constant time。🤧嗯。

So we're gonna have to develop some techniques to get around that， Okay， so。The basic。Issue。Is。How。

Do we。Search。A single。Fusion tree node。In constant time。So with thenM Boaz trees， you know。

 using the word RA model， we exploited the fact that keys were themselves also kind of memory addresses。

 and that's how we were able to beat this。Comparison based lower bound。Here。

 we're going to go way more overboard with using the power of the word Ram model。 Okay。

 so you're going to see a lot of bit tricks in this lecture。so。So the basic ingredients。姐。Wello。

We're going to use multiplication， we're going to exploit the fact。Now we can multiply numbers。

In constant time， as long as they fit in a word， you'll see where that's going to come in。In fact。

 there is a version of。There is a version of fusion trees which avoids multiplication。

 which came later， but I'm not going to present that。We're going to see sketch compression。

So there has to be some amount of compressing of the keys because we just said that all K keys can't even fit in a single node。

 so we can't hope to do it in constant time。 We're gonna have to somehow compress these keys。

We're also going to see word level parallelism。So at some point。

 when a query comes and reaches a fusion tree node， we have to see where it fits。

 which subte we have to recurse to。And we're gonna eventually do that by comparing with all keys simultaneously using a constant number of word operations。

Okay。And somewhere in there， we're going to also。嗯。Look at。Well。

 there's going to be a very basic subrtine we're going to need。

 which is the most significant set bit。AndWe're going to show that。

We can do this quickly and that we can use it to do some of the other things we want to do。 Okay， so。

 I mean， just so we're all on the same page in a w bit word。

 how long does it take you to find the index of the most significant set bit。With any algorithm。W。

 right， So what do you do， you kind of loop from the W minus first bit all the way down to the zero bit。

And then you， you know， you do a。A bit wise and and mask out that bit and see whether the result is zero or not。

Okay， so can you be W？Give me anything to B W。How would you do logW？Yeah。And so yeah， you do。

 you do binary search to figure out what's the largest I such that your number is bigger than  two to the I。

And 2 to the I is just one bit shift I positions to the left。 So that's all constant time pereration。

So we're going to see this in。Constant time。Okay， we're going to show that in the word around。

 you can actually do most significant have been in constant time。That's gonna be。And it's not。

It's not going to be as。Easy to explain， but we'll do it okay。Okay。So。Yeah。I think about it though。

 when I say constant time， like on your computer， you'll probably never deal with。

Types that are bigger than 64 Bs， like 64 B ins Lo of that， I guess， is6。

We probably will'll have a cluster set of operations， but I think it'll be more than six。

 we'll count what it is。We'll count what it is when we get there， but。You know。

If ever you deal with like 1024 bit to answer something， then or no， maybe larger。

 I don't know what will'll have to。Due to beat the logW bit。Okay。So good。

So let's start let's start attacking these things。 So how do we search a single fusion tree node in constant time well。

Before we get there， we need to make sure that we even fit a fusion tree node into a single word。

 okay。So here's the basic idea。 so remember that。I'm not counting really preprocessing time。

 This is a static data structure。 I'm allowed to do whatever computation I want， okay。

So the first thing I'm going to do in the very beginning。Is just sort everything。Okay。

 and then just build the tree with exactly k nodes per internal node。

Then now I know what the nodes are， what the elements are in a particular node。

 and I want to figure out how to form that node to fit in a single word。Let's focus。On representing。

singleing。Fusion tree node。And it contains。Kay keys。X0， less than x1。

 less than that less than x sub K minus1。Okay。So。Let me draw a nice picture to convince you that we can get away with using。

Les than w to the six fifth bits to represent a single fusion tree node。So when you draw。

Let me draw a path。So let me let me first write this， one，0。1，1， one。0，10。Okay。

 so let's say that that's。Some element， that's one of the Xs。Okay。

 so I'm going to first draw vertex here。And then I'm going to go from the least significant bit to the most significant bit。

 When I see a 0， I go left， When I see a 1， I go right。 Okay， so I see 0。I see one。0，1，1，1， that's0。

1，1，1，0。1。Okay。And then there might be some there are some other excs in here。

 so there might be another one that looks like this。I guess zero。0。Well， well let me draw it。

So what's this？This is zero，0，0，0，0，00，00s， that's five zeros。And then a1 and then a0。

And then I might have another one that maybe branches off somewhere down here。是。

So I can draw some collection of。So for example， here。K is3。

 so I have three X's that I'm representing in this way。And the thing to note in this picture。

Is that in order to differentiate， So in order to differentiate the X's。

I only need to look at vertices where there's actually some branching。Right。So。For example， this bit。

So this is the second bit， like this is this bit here。And also this bit。Which is the0，1，2， three。

 fourth bit，01，2， three， fourth bit。Just maintaining remembering those two bits is enough。

To differentiate all the Xs， okay？So。I can define， so let me write。Let R less than K。D the number。

Of kind of branch bits。And let。Their indices。B0 less than B1， less than that， less than B R minus1。

So these are kind of the only bits I need to know in order to distinguish the X's。

 And if I just project down to those bits。Then。It maintains the ordering of the exc。I mean，'' worry。

 we're not anywhere near done。There's a lot to- there are going to be some issues that we're going to see very soon。

And I'm going to define a sketch。A sketch。呃。Sketch。SK of X。As。keeping。Only。The XB。Okay， so。

 for example， I mean， it's a function。 Also， you know。

 the sketch function depends on the whole set of the Xs because it depends on this picture。

So for example。sketchketch。In this particular scenario， if I'm sketching 1，0，1，1，1，0，1，0。

 I'm saying I only remembered that bit and that bit， that's just equal to 11。Okay。So。

So now going back to。Fusion tree nodes even fitting into a single word。呃。Each Xi。

Has sketch of X taking。R using up R bits， but R is just at most k minus-1。

 So that's also w to the15 bits。Implies。Can store。All of the sketch of X's。In K times R。

Which is O ofW to the two fifth bits。Okay。So at least the information。

It can can fit into a single word。嗯。Now there are going to be some issues like， for example。You know。

 there is no single， there's no C operation in which so we could。

 we could easily mask out in preprocess。 We could create a mask， right。

 Each fusion tree node could store the mask， which tells you what the important Bs are。

And you can convert Xi into just remembering the important bits by masking out everything else。

Just ending with the bits that matter。But that's not going to compress things。

 That's not going to remove the bits that don't matter。 And there' is no C operation， which says。

 compress into these bits and put that into a new word。

So we're going to have to deal with that at some point。嗯。

There's probably a more serious issue though。Which is that the query element doesn't need to be one of the X's。

Right。So let me draw an example。嗯。So let's say there are four bits。Okay。So imagine the bits。

 imagine that the x size that we're actually storing are the following， one is 0，0，0，0。

 so w here is 4。What is0，010？One is。1，10，0。And another is 1111。so in the tree。

 the things that matter here are。So。What are the branch bits that we're actually going to remember？

Well， there's a branching right here。And there's a branching right here。 It's the same bit， actually。

And there's a branching at the root。 So there are two。There are two branchch bits。Okay。

So it's the zeroth bit。0，0，8，0，0。0， zero。Okay， so sorry here was。Forgive me。

m here I'm imagining that I'm reading from the left。Okay， so。0，0，1，0， so 0，0，1，0。

 reading from the left。Yeah。決戦？But the branch。えミ起きアで。Or do you start the branch？Only that。

Probably that exciting。 I mean， so I just defined a function。So each fusion tree node。

Has its own sketch function， depending on all the set of excs that live in that fusion tree node。

Yeah， okay okay。Yeah， yeah， yeah。Will you start。John Schwitz。X0 is not in。Yeah， yeah。 you will。

 So there's a set of branch bits which matter for that node。

And all Xs in that node will be projected to those branch bits。

 even if it's not where Xi itself branched。Does that answer your question？Okay， so okay， good。

So the zeroth and the third bits from the left are the ones that are relevant here。

 those are the branch bits。So here it's 11，10。Zero1 and0， zero。

 that's the sketch of every single one of these。And then now， some query can come in。

 which could be totally different， okay， so。Well， let say let me show you what I mean。

 so imagine a query comes in like this。Like this。Like this。And like this， so this is01，01。

This is our query。谁。And what's its sketch？It's 0，0。Okay， so in actuality。Q should be between。

 remember that the reason we're trying to find out where we fit in these X eyes is to know which subre to recurse to。

😡，So really， Q should fit in the subte between these two items。

That should be where we're going down to。But。Sorry， sorry， no， no no。

 It should be going down in the sub between these two items， right。

 because the query node is actually between this and this。

But its sketch makes it look like it's between these two。So that's not good for us。

So that's the first thing we're going to。Fix right now before we move on to。Fixing other things。

It's going to be， I think the easiest thing to fix。Questions about anything so far？Okay。🤧So。

And of the。The insight here is to look at the first bit。Where things went wrong。

And what do I mean the first bit where things went wrong？

Things went wrong because we weren't storing a branch bit that we really should have been storing。

Okay。And that's right here。😡，はい。upp until that point， the branch bits we were storing。

 namely this one were keeping us on the right track。

 but then Q branch somewhere where we didn't keep information。So。嗯。Suppose。Sketch of Q。Lies between。

呃。Sketch of。X I and sketch。With X plus one。Okay。It does not imply that Q lies between xine x cycle plus 1。

 but I claim that。We can still use this information for our benefit。Okay。

And the way we're going to do that。Is as follows。嗯。嗯。Let why。Be the node。Where。Q falls off。

The highlighted。Paths name。The first node。So this is our why here。there are two cases。

Either Q is going to fall off and go to the right， or it's going to fall off and go to the left。Okay。

So。If Q。Falls off。To the right。Set。Yi。He's going to be a new word。To be why。By y， I mean。

 look at the bit stringing， the prefix that's defined by this node。

 so here y is just zero because we went left zero once okay。This node would be 01， for example。

We'll let E be y。Followed by 0， followed by。A bunch of ones。Otherwise。If Q falls。To the left。Let yi。

Y1，0。谢。Okay。And the claim。Claim。Is。If。We。See where。Sketch of。Efits。Amongst。The X。系。That。Is the same。

Among the sketch of Xs。Or even E itself， that is the same as where。Q。Fits。Amongsts。The Xi。

Which is what we actually want。So the way we're actually going to do this is we're not going to。

We're not just going to recurse into the two things that the sketch fits between。Okay。

But what we find where the sketch fits between， we're going to form this E。Then we're gonna again。

 run a comparison with this E。And then we're going to use that result to tell us where to go down。

Okay。Are there questions about what we're doing？Yeah。Oh，That's a very good question。Okay， so。

So I claimed that if we had number four。We can do that， so do people all agree？How would you。

How would you use this number four to？We haven't done them for you yet， but yeah。beや the model。

I sorry to say it again of the not。I mean， it depends on how we're present the mask。

The those that we're keeping other one。E one you take。おデルのす。Oh yeah， I mean， let's pretend。

 in terms of masking， let's pretend that we actually somehow were able to compute the sketches properly。

Okay， we already have the sketches right。嗯。Yeah， we already have。Okay， yeah。 So we have the sketch。

 but we also have the X size  too。 Okay， so we have both of them。 So now what would you do。Okay。

 so let me write that here， so first of all， this proof， I'll leave it to you as an exercise。

But you're saying that to find。Why。Okay， you do what？X X or， is that Xor， it is Q？不。Yeah。

People agree， people。See what's going on here。So XX or Q is telling you the bits that are different。

Okay。And the most significant bit is telling you the first bit that's different between the two。对哎哎。

I'm sorry。You would do， Yeah， no， you're right。 You would do this to the actual X I。

 as you were saying， You would do this to the actual X I。

 and you would do this to both X I and X I plus1。Okay， to see where you first fall off。Okay。

 so compute。The most bit of X X or Q。The most significant bit。Of Xi plus1， x or Q。Okay。

And then just take the more significant of the two。

And that would tell you the first time you fall off between the two。

And here we're just using the fact that the bitwise xor is just telling you which bits are different。

OkaySo we're going to have to eventually come back to。呃。

Dealing with how to actually do most significant bit。 But we're going to do that at the very end。

Okay， any other questions？Yeah。嗯。Let me think。I mean， but it could。Okay， I guess。嗯。

So let's say what you actually know right， so you know the sketches。It could。

 It could be from the sketch。 Yeah， So okay， So when you're falling up to the right。

 I agree with you， I think， but。You still have to compute this Y using this most significant bit。

 like how do you know what Y is， which is the original question。

To know that you fall off to the right， you would have to know what Y is。Oh， I see。

I see what you mean。 Yeah， I think what you're saying。Sounds plausible。あ。This might be the case。

 yeah。Okay。Any other questions？Okay。So anyway， so that's how we。

Use sketching to help us find where we should recurse to。呃。But of course。

 there's an issue I raised in the very beginning， which is。

We don't have a sea operation which makes sketches for us。不认。

So here we use we're going to start getting into the power of multiplication。Okay。And。You know。

 why did I choose this W to the one fifth right now。

 were we're pretty we're using way less space than we need to use。

 I mentioned that sketches fit in W to the two5s。Okay。Problem。You know， how。Do we form？Sketches。对。

And the idea here is we don't need to actually do sketching exactly as I said it。

 So one way to do sketching is just to mask out the important bits， the B of， the B of I。Okay。

That we can do just by a bit wise and with a certain string we create in preprocessing。

The problem is that doesn't do any compression。After you do the and， you still have w bits left。

So perfect compression would get us down to this W to the fifth。

But we don't have to get W to the fifth either we're allowed to be somewhat looser。Okay。

So we don't want W， but we we can get away with worse than W to the fifth。Will。Compress。down。To。

R of the fourth。Bs。Okay， so we won't get orbitbits， but we'll get R to the fourth。

 R of the fifth is W。 We don't want W。A。And。The important bits。Will be represented。With some。Noown。

Amount。Of zero spacing。In between them。Okay。Whats。So if you mask， it still takes W bits。

And the number of items is W to the fifth。 you're still taking W to the sixth fifth space。

 bits of space。I want to do some amount of compression。メスなって言くまさた。Yep。Space shifting。はいまあ我。Okay。

 so it's true that we can preprocess the X's to make them look nice in their sketches。

 but Q is coming online as a query。So whatever sketch we do has to be applicable to Q in constant time as well。

Does that answer your question？But that's a good point， Yeah， in preproces。

 we could make these perfect sketches that took exactly our bits。On the X eyes。

 but then when a Q comes， it's not clear out。How a sketch that on the flight。エサイズ？Oh， we will。 Yeah。

 we'll store them and we'll store their sketches。 Yeah， but we won't。

 We won't store the fully compressed sketches。 We'll store some sketches that have some amount of spacing in between。

 but they'll still take out most out of the fourth bits each。Yeah。

 so if we're storing the full exerciseise， why are we？There is also。I mean。

 the way that we'll define sketches， you can compute the sketch function in constant time。

 So you don't need to store the sketches。 I mean， you could store you could store them。

 You could compute them on the fly when you need them， but it it still， it' still be linear space。

 even if you store them。Like for each X， storing it and its sketch would just be an extratro。

You also do。Oh， oh， okay， so。Right。So。We're still not to the point yet where I've told you exactly how we're representing a fusion tree node。

 but the point is whatever we're storing in that fusion tree node。

 when a query element comes into that node， it needs to decide in constant time where it's going to go so。

There are going to be certain。Carefully crafted words。

A just a constant number of them that we're gonna in pre computationut。

 we're gonna to place in that node so that we can do that decision in constant time。

 So I haven't told you what exactly we're going to store in that node。

But it's going to involve the sketches of those X eyess。And we're going to get there soon。

This word level of parallelism is to do kind of parallel。Comparison。So at some point。

 Q is going to come in。 and in constant time， we're going to decide exactly how like which index it lands between。

 So we're gonna have to compare against everybody kind of at the same time。Okay。So。Question。か才。我们最。Y。

E would give you。So E itself would be， whereas y。 So y is 0。 It'd be 0，0。One， one。

 it'd be the rightmost thing in this tree。That you would be。Say E were one。00 zero。Then。OneIt be10。

 one it would be 10，0，0，0。Wait， wait， hold on， so you're saying let me just make sure I'm so you're saying suppose the query instead were。

So like suppose you query with this。Okay， so you fell off。

 so where's the first branch node you fell off？What here， but， this is a branch node， though。てな。

But this is also oh， this is yeah correct， This is not a branch bit。 Okay， good。

 so this would be your why。So E would be y0。これだけ好かって。So you fell off to the left。Which means that。

E should be the。Yeah， it should be that。So it should be 11，0，0， so this would be E。Right。Okay。

But this is not a problem， right。完全。世験感たらげ。さいてます。Yeah I think yeah， I think this is not a problem。

And。AndAre there any other questions or should I keep going？いさいす。詳材？ャ。Yeah。Right， so at that point。

 you could do what a new gen set and just actually compare those。

 They are only now like kind of two possibilities。 so you just can compare them and see。同事。

So now we're going to use multiplication。So here's the idea。Takeick。So。Suppose。We multiply。

X times some。Some M。🤧Okay。Where。呃。X is equal to the sum I from 0 to r -1。

 So let's say we've already now masked out to only keep the important bits。Okay。

It's the sum of some Xb times 2 to the B。And y M is equal to sum over I from 0 to。

 we're going to have only one R positions in this M2 to the MI。ok。So the question is。

 how do we we're going to choose the MI to get something nice。All right。And the BIs are increasing。

 the MIs don't think of them as increasing。That eyes are arbitrary。So lemma。We can choose。The MI I。

Such that。嗯。A。呃。For all IJ。Well。The set。Oh my right I like this okay。All the B。Plus MJ。Are distinct。

So there R squared of these sums B。B0 plus m0 is less than B1 plus M1 is less than do dot is less than B R minus1 plus mR minus1。

And see。If we look at the range。How many bits are spanned from？The biggest index， the smallest index。

That's going to be our of the fourth。BR minus1 plus R minus1 minus B0 plus M0。

That should be O of art in the fourth。And before I approve the dilemma。

 I just want to say why this is going to be relevant for us。 so the point。Is that？

So's let right to the point。Is that。X times M。Is equal to if you just expand out that product。

It's the sum from I going from 0 to r minus1， the sum j goinging from 0 to r minus1。

Of Xb2 to the B plus MJ。Right？Now。As long as the BI plus MJ are all distinct。

None of these powers are the same， so we don't have to worry about carries。😡，Okay。嗯。And now。

 once this holds。Basically， what we're going to do is we're going to。

We're going to only use these R bits。😡，Our sketch is basically going to be projecting onto these。Los。

 B0 plus M0， B1 plus M1， et cetera。Okay。And we're going to mask out everything else。

And notice that the range between the biggest location and the smallest location is only R of the fourth。

ok。So after we're done masking， we can shift everything down so that now this fits into a sequence of contiguous bits。

Starting from the right， that's art of the fourth long， okay。So we have to do this。Okay， so。So yeah。

 any questions。So you send the MI。現形ジ。人。Yeah， minus。Yeah， but there's property B。

 which says that the sums are at least increasing。Yeah。你别。It may already be blessed。

BI plus MI less than2 R。 BI is not less than R。I mean， sorry。Yeah， BI is not less than our。

 BI is at most W， and MI will be at most W2。Yeah， yeah。

s not it's not the case that this is less than R。 It's just that if you look at the range of bits that are important。

 they fit into a contiguous block of it most size of most R of the fourth。 but once that's true。

You can shift them down to be the first art of the fourth bits。So initially。Yeah they。They're w bits。

But among them only are。So that's right， So should x。

 you should think of x as being one of the Xxi's。But we've already masked out the BIs。

We're only keeping the important bits。And那。And then now we're trying to compress those bits。

Into fewer locations， or into。A smaller width of locations。Okay。Yeah， so property B looks like it。

Considers cases where I equals。That's right， that's right。because。Well， so。

 the ideal sketch of x has R bits。Okay， and what I'm saying is these are going to be。

These are going to be where we'll read those orbits off from。

So if if you want XB for I between0 and R minus-1， if you want XB。

 just look at the power of 2 which corresponds to B plus MI， that's what I'm saying over there。

So we're really just。The sun。So， I mean， we're actually computing X times M。Okay。

 because that's the thing we can do in constant time in Word RAM。But I'm picking M in a special way。

Such that。So X has its， you know， itss R important bits spread out。 They could take。

 they could span the entire W bits。 There could be some huge gaps between them。

 But after I do x times M。And then mask out only these locations， these are locations。

What I'm telling you is that those are important bits are now compressed into a width of length。

 almost R to the fourth， which is w to the4 fifths。 So they started off spread in a width of W。

 Now they're down to W to the4 fifth。How are you going to。In pre so in pre processing， I'm gonna。

 I'm gonna find， I'm gonna we' gonna see how to find this M in in the proof of dilemma。

 So in preprocess， I'm gonna find this M。Okay， and then I can create the mask in preprocess。

 The mask is a single word。It's a single word which just has ones at these R locations。

And to mask those out， I just do a bit wise and。So I'm going to do x times M。

And then I'm going to do a bit wise and with the mass containing these our locations。

 and I'm going to shift it down。 That's going to be my actual sketch。Yeah。This lemonmon you。一緒のテに。

The MI is no， they're not they can be anything， yeah。Any other questions？到这。So， so yeah。

 so what's the point here， The point is。We first。Mask。The B is。Mass the important bits。From Xi。

Then we。Do。😔，To get X。Then we do x times M。And then we mask。Out the bits， B plus MI。

And then now we shift down。So that。B0 plus M0 maps to bit0。It' the least significant bit。

So we're going to shift down by B0 plus'0 at the end。

And then this thing tells us that now it fits in art of the fourth it。Okay， so let's prove a dimma。

So we're going to do part A first。Okay， so。So， part A。So we're going to prove by induction。Suppose。

We've already picked。M1 prime， M2 prime。Mt prime or t minus-1 prime。Such that。All the sums。

BI plus M J prime。 So these are not going be the final Ms。 but these are the MJ primes are distinct。

Moud are cubed。Okay。Where。T is less than R。Now， I'd like to pick。Now。We want to pick。MT prime。

So the thing that I want to show by induction is that we can choose M1 prime up to M prime minus1。

So that all the sums are distinct mod cubed， okay。So now I want to pick MT prime。

And in order to make sure that all these sums are distinct， we need to make sure that。MT prime。Plus。

 B。Is different from BJ plus MK prime。I'm already using in K plus M Z prime。Okay， so。MT prime。

Must avoid。Am I prime。Plus minus Bj plus Bz for all the other different values， I J and Z。

But how many of these values are there？How many of the Bs are there， how many BIs are there？

So this is r squared， and then there are t of these so far。See the t squared R values。

But we can work over。A cubed values。This is less than r cubed。Because we're not done yet。

Which means that there's something we can pick， which avoids all of these。Okay， so。

We can choose we can choose all these MI primes。To make the sum's distinct mod cubed。

 and then now how do I actually choose the MIs？Well set。And I'll draw a picture。 We'll set MI。

To equal。Am I prime？Okay。Plus。I times r cubed。Plus。W minus B。Rounded down。To the nearest。Multiple。

Of our cubed。So the picture to have in mind。This is the final picture that we'd like to have。

Is that we have these blocks of length RQ D。Okay。And all of these MI primes are values between 0 and a cubes minus1。

😡，OK。And so we have some BI， the thing that we want to have is kind of B0 plus M0 is somewhere in here。

B1 plus M1 is somewhere in here。 B2 plus M2 is somewhere in here， et cetera。

 that's why we add on this I times R cubed to shift us over by R cubed each time so that things are in different blocks。

But so it's true that plus B+。MJ primes are distinct to mod our cube because that's how we formed the MJ primes。

But in order to make sure that。With the M's， they're still distinct。Right？

That's why we did this rounding down to a multiple of R cubed because it's MI prime plus that's a multiple of R cubed and that's a multiple of R cubed。

😡，So everything mod cubed has stayed the same。And that means that B plus MJ。😡。

Modarch cubed is different。So in particular， B plus MJ are different。Okay。

 so that's why we satisfy property A， they're distinct， even mod cubed， so they are distinct。我。

And kind of this， we want this property that B0 plus M zeros are increasing。O。🤧So。嗯。Well。Yeah。

 I mean， they're all， I guess the picture I said is exactly what this does。 Maybe you can。

I don't want to spend time on TDM， but。This picture will exactly put kind of one guy in every single clock。

Z。Kind of subtracting， subtracting B I would just。Make things negative。嗯。So。

We put the W to prevent that。Yeah， this might take up a still will take a constant number reward words。

But that's okay for us。Right and there might also be some junk here that we don't care about and also some junk here that we don't care about。

But at the end， we're going to mask and shift everything to the right anyway， so we don't care。Okay。

 so。That's how we're actually going to do sketching。So now。So I defined how to do a sketch。

And we can actually do the sketch in constant time because to do the sketch， it's what。

 It's multiple。 It's a mask， a multiplication。Another mask and a bit shift。

So a sketch is like four operations。Each taking across a number of words。Okay。Good。

 and in pre process， Okay， so now going back to a question that I guess you asked me a while ago。

 what are we actually gonna store at a fusion tree node。Okay。呃。Now that we have sketches。

Suppose node。Fsion tree node has。X0 less than less than x k minus1。

One thing we're going to store is the following word。Which I'm going to say。The sketch of that node。

Is equal to。1。The bit one。Followed by the sketch of x0。One， followed by the sketch of x1。

And then one， followed by the sketch of X 1，s k 1。Okay。And now we want to know。A query queue comes。

Where does Q fit？Which subt should we recurse on？So I'm going to define the sketch。Of Q。

 the sketch to the K of Q。As being。0。Sketch of Q。And。嗯。Right， okay。0， a sketch of Q。0， sketch of Q。

And what am I going to do？I'm going to subtract。Okay。

So tell me what happens within a So definitely there will be no carries going from block to block because。

Just this part。Is bigger than this part because that's a one in the M。

 the most significant bid ofness is 0。What am I going to get？I'm going to get either a 1 or a0。😡。

Followed by some stuff that I don't really care about。

A1 or a0 followed by more stuff I don't care about。Okay。And then I'm going to mask out all of these。

I'll get a1 or a0 followed by zeros。A1 or a0 followed by zeros。And then a 1 or a0 followed by zeros。

By the way， so I'm forming this in preprocess。Q comes on the fly。

 How I How do I form the K power sketch of Q。Yeah， right you multiply by a number that has one here。

 followed by zeros， one here， followed by zeros， one here followed by zeros。Okay。

 so that's a single multiplication。Okay。And now if I want to know where I land， what do I do？

I think the most significant bit。Okay。And that's correct， but I'm going to do it a different way。😡。

Okay， and the reason I'm going to do it a different way is because。

The way I'm going to do it is also going to play a role in how we actually do most significant bit later so there' will be some circularity if I say do most significant bit here and then when I say to do most significant bit。

 I'll say do it like how we did it here。嗯。And the key insight is。Kind of the number of。

The number of kind of bits here that we care about are there K of them。So if we can。

 and it's monotone。Right， it's going to be， so let's say the。It's gonna be。

 I guess these are the smallest numbers。 These are gonna be。What should I say。

 When is this a one and when is this a 0。It's a zero。If we had to carry this one。We carry this one。

If this sketch is less than that sketch。So this is a0， this bit is a0。

If the sketch of Q was bigger than the sketch of x0。So it's going to start off as0 for a while。

 and then it's going to be a one。 And that first one is going to be the first thing we're smaller then。

Okay。That's why finding the most significant bit is the right thing to do。

So the point is that this is monotone， so finding the position and there are K of them。

 So finding the position of the first one is the same thing as counting the number of ones。

If we know how many ones there are。That tells us where the first one is。

And how are we going to count the number of ones？We're going to multiply。Okay， so。So。

The appearance of ones。Is monotone？And that implies can just count。The number of ones。To find。

The index。Of the first one。So remember we want。We want。The most significant bit。Of that thing。

So what we're going to do。Is we are going to multiply。By。

 let me make sure I don't tell you the wrong thing。Yeah， yes， it's just this thing。1，0，0，1，0，0，1，0，0。

 and then one。0。We're going to multiply by this thing。And what that's going to do。Is。

It's going to take this， so this one here。Right。Will appear here。If you multiply that。

 it'll appear here， here， here， and here if it's a one。And that will get added。

 So then if this is a one。That one will appear。Here， here， here， et ceter。And the point is。

When you do the multiplication， all the things that are one。😡，Will contribute by adding。

 starting at this position。Okay， so。All the ones。Contribute。By adding that position。

So then what you can do is and they don't interfere with each other because this count is a number between 0 and k。

So it's going to consume at most log K bits。Whereas what's the width of this block。

 The width of this block is like。K to the fourth or something。Okay。

 so there's no chance that these things are going to clobber each other。Okay。So what you do is。

You look at a log K width。😡，Interval of bits around here。

You mask everything else out and you shift this down to the beginning。

And that number is exactly the number of ones。Okay。Good。呃。I think that's。

 that's the word level parallelism， What I meant by parallel comparison。 right， Basically。

 we compared everything at the same time in single。

And a couple of a constant number of machinery operations。Okay。

 so now the only thing left is computation of the most significant bit。

And the way we're going to compute the most significant bit is， again， using multiplication。

 sketching and word level parallelism。As well as this idea， okay？😊，so。

Now that you are masters of all these ideas。I'll just sort of tell you。How this goes。

So the basic idea。Is。Split， so let's say we want MSB of X。We're going to split X。Into root W chunks。

Of root W bitsch。It's not going to be recursive like Venom go as this is the one time thing。Okay。

 so for example。If I write x being。01，01。0ero， zero， zero， zero。1，00， zero。1，10，1。So here。W is 16。

 and root W is 4。 This is the first chunk。 This chunk is chunk， this chunk。

And what we're going to do is first。First， using word level parallelism and multiplication。

 et cetera。We're going to figure out。😡，Exactly。We're going to form a root W length bit string。😡。

That's consecutive， which will tell us exactly which clusters are non zero。

Which clusters have anything in them at all？And then once we， once we find that。

We're going to find the first non0 within a cluster。

we're going to at some point exploit the fact that we can deal with root W size numbers。

 We can do crazy things to them really fast， okay。Okay。So， good。

So the first thing is I'm going to create F。Which is 1，0，0，0，1，0，0，0，10，0，0，1，0，0，0。Okay。

 why am I doing that？I'm going to do X。And F。Bitwise and。Is that mid wise and， I don't know。Okay。

Yeah， that looks almost much like XO。 So that is going to。Look like this。

 and let me right after I write it， I'll tell you why I'm doing this。

So what I'd like is some summary that tells me which clusters are non zero。

I'm going to treat the first bit as a special case。Okay。

 so now I know I I know for sure that this cluster has an non0 and this cluster non0 has a non0 in particular because they have it in their first bit。

Okay， so I'm going to deal with the first bit of a cluster and the remaining bits in a separate way。

 and the reason， the reason I want to do this is because remember when I did the parallel comparison。

I exploited car and subtraction。Right， and in order to do that carry and subtraction trick。

 I needed to have room to have an extra one bit at the beginning of every cluster。

So now I'm going to clear now that I have this information handy， which I can look back at later。

 I can clear it。And deal with everything else。 So now I'm going to do with， I'm going to do X。

X or x and F。Which just clears all the leading one bits。 So we'll have 0，1，0，1， just like this。

 we'll have 0，0，0，0。We'll have0，0，0，0 as we clear the leading ones， and then we have 0，1，0，1。

 so we clear the leading ones。Okay。And now what I do。Is。I will take。No。🤧。

I will take F minus that thing。Okay， so what does that look like？So， F。Looks like 10，0，0，1，0，0，0，10。

0，0，10，0，0。And X。Bitwise x or X and F。Looked like， well。

 it doesn't have any ones in the leading positions。 It looks like 0，1，0，1。0，0，0， zero。0，0，0， zero。0。

1，0，1。And I do a subtraction。Okay。Which blocks， So within each block。

 definitely the F block is bigger because it has a one and a most significant bit because we clear those in in the X thing。

嗯。So the cases where this one gets borrowed are exactly the cases where the block is nonzero。

If the block is not zero， it gets borrowed。So here it will get borrowed and it'll have zero times some junk we don't care about。

Here it doesn't get borrowed because it's empty， so we have one in some junk， one in some junk。

 zero and some junk。Okay。😊，And now we mask and get rid of the junk。And then we have0，0，0，0，10，0，0，10。

0，0，1，00，00。Okay。We mask out all the junk， and then we ore back in。That。

Why do we order that back in because this tells us which clusters are non zero。

 but I lost all information about the leading bit in the cluster。

Now I want to get back that information about the leading bit。So I or back in。X and F。And then。

 I get。0，0，0，0，10，0，0。10，0， zero。1，0，0，0， great， so now I know。Exactly which clusters。Are non empty。

 The clusters that have a one in the leading position and 0 L。 So this cluster。

 this cluster and this cluster have stuff in them， yeah。呃。Yeah， that's right。 I should do。

That's right。 I should do a mask and a knot， as well。Right， I should。 I should not and then mask。Yes。

 yes， I can also x with F。That's a good point。Yeah。And then I exor。With F， and then I because 1，0，0。

0。0，10，0，0。0，0，0，0，1，0，0。啊，是啊。So now this should actually have been a one， I think。

And that should have been a zero。You know， something like that。But yeah。

 you should have negated and then masked out。 That's a good point。

But the bottom line is we have these root W sized chunks。 Each one has a one in the looing position。

 if and only if。That cluster was not empty。So now what I want to do。Now what I'm going to do。

I I'm going to sketch。But I'm not going to do a sketch into R of the fourth。

 I'm going to do a perfect sketch。And it's going to be， again， the multiification， lemma。

ThereSo the point is， originally， the Bs were just arbitrary。

 Who knows where the important bits were， right， They depended on the branch bits。 Now。

 we know what the Bs are。 Theyre root W -1。2 root W-1，3， W -1， okay， so。When。The B。Or。呃。

I root W plus root W minus1。There is an M。Such that。Multiplying。By M。Makes。All the important bits。

Bits。Consecutive。With no gaps。Okay。Proof， I think that will end up being on your homework。

So now what do we have？We're almost done now what we have？

So I'm telling you that I can form a word that has this 1，0，1，1 consecutive。1，0，11。

Which is just the leading bits in each of those clusters。In constant time， right。

 we can do that by multiplying by M and then。And then doing some shift and masking。Okay。

And then now what do I do？Now I need to know。What's the most significant bit in this word that tells me the first cluster。

That has a non zero。I want to know the first cluster that has a nonzero。So。Do parallel。Comparison。

Between。This 1，0，1，1， and。The set of words，0，0，0，1，00，1，0，0，1，00，10，00。Each one is root U wide。

 I w wide， they' root W of them， they fit in a word。Even when you put those extra ones in between。

 remember to do parallel comparison， you had to put these ones and zeros stop measures。

 It still fits in two words。Okay。And you do a parallel comparison with this vector repeated a bunch of times。

 you'll find it out。Now you know the index of the first cluster。So。

The first cluster happened to be this one。Now， what do you do， again， that fits in root W bits。

 right， You can just shift that down。And again， you do a parallel comparison with these。

Root w things。And then I know my most significant bit。So that's all the details。

 except they didn't improve the dilemma。Which I guess you'll prove yourselves。

So that I think that's the end ofussion trees。对。I'm not sure。How do you form this？Howi from this。

 you multiply by。A word which has 100，0， 10，0， 100， 100。I'm sorry。Right， but。

 but we know how to do that because， right， So we， we said that we can find E by doing a most significant。

 Yeah， That's right。 Do this with E。