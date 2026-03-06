# 加州大学伯克利分校【中英⚡数据流算法｜CS294 Fall 2020, Sketching Algorithms】 p06 P6 Lower bounds via communication complexity -BV11zi7BjEHu_p6-

![](img/9bb2c7274eabb1ad9fd7085567c3b272_0.png)

So today。他过。Wrap up discussion on lower bounds。And then start a discussion on turn style。

TThe turnsdown model for streaming and sketching in the turnsdown model。Particularly there。

 we're going to talk a lot about。Then you're sketching。

So I mentioned in class on Monday as well as in the11 lecture notes that there are generally two methods of proving lower bounds and sketching algorithms。

 one is this compression type of argument， which I gave a few examples of on Monday and there's one more of quantiles in the notes。

And the other is communication complexity。So。Today。

 we're going to talk about that communication complexity。So。The idea of communication complexity is。

 well， it's a model， Okay， it's a computational model where you have two parties often they're called Alice and Bob。

And Alice has some input。爸 has什。And they want。To compute。Or determine。

Some function apply to their inputs。And， you know， there there are variations on this where instead of two players。

 you might have end players， each player has their own input and you want to compute or determine some function of all their joint inputs。

 That's a possibility。 And the model here is Alice and Bob basically talk back and forth。

 So Alice sends Bob message。Bob sends Alice back a message， Alice talks back to Bob， et cetera。

 and then kind of the last person who receives a message in the conversation then says aha。

I'm now convinced that I know of the XY and then they output put the answer。And the goal here is to。

Minimize。Total communication。You， this is communication in blood itself is you a broad。

A very active area where people study various things。 So minimizing telecommun is one。

 you can also like， you know， want to say， you know minimize you know minimize the number of rounds of communication that's another thing that people like to do。

We're studying in more restricted models where you say， look， I only allow one round。

knowWhat's the minimum message length in one round that's achievable or bound you know bound the number of bits per round and now argue about the number of brands you need etc cetera。

 so there are various like twists on this， but this is the essential idea。And there're also， I guess。

 I will say。A few different kind of sub models。 So there's deterministic communication complexity。

There's randomized。And within randomized， there's public versus private coin。And another one is。六四。

Dributional。Where in these two。The input is worst case。Whereas here。The input is random。

From some distributors。So X and Y are drawn from some distribution view， for example。

So you can ask these questions about what's the minimum amount of communication necessary？

For deterministic protocols that solve this problem or for randomized protocols that use public randomness。

 public randomness， meaning there's a public random string in the sky that Alice and Bob both know and they can both use it to determine what to send versus private coin means that each are flipping their own coins privately to determine what to do but Alice doesn't know Bob Bob's coin flips and Bob doesn't know Alice's coin flips。

 Of course， they can share those coin flips by sending it as a message but that would cost you right then you're trying to minimize it number thats you send and then distributional is also。

Basically distributional model， you can assume without loss of generality that。

The protocol is deterministic。Okay。AndAnd。And the input is random and you're trying to succeed in computing up with as high a probability as possible while minimizing communication。

啊，O。你好。嗯。Why is communication complexity relevant for proving streaming lower bounds。

 the basic idea to the connection between communication complexity？And streaming lower bands。

So what's the idea here？The idea is basically he'll show。That if。

You'll draw draw a reduction if computing F。F。Is hard。In in a communication model。That。

Actually like this。诶咁面大个得。Sure I'll say if。嗯。Cons solveve。Problem P， let's say， in stream model。

If you had an algorithm A。Then， it's possible。To use a in a black box way。To solve some function F。

In the communication model。So we have a reduction， therefore。If F is hard。

 meaning it requires a lot of communication。Then P must be hard。And typically， of course， the。

You'll see an example soon， the amount of communication in the protocol that uses A as a black box。

The number of bits sent。Will depend on the the amount of memory that it uses So for example。

 the protocol will be。Alice will look at her input， think of her input as being part of a stream。

 run A on that stream， take the memory contents of a， send it as a message to Bob。

 and then Bob can somehow use that to compute the answer to F。So， example。

Is F is the equality function。let's say01 to the end。So。A of X， Y。Is one。If x equals y and 0。

 otherwise。So a theor on which I won't prove today is that。The deterministic。

Communication complexity of equality。Is at least Ed。There's basically。

 I mean there's there's a trivial protocol， which is that Alice can just send her entire input。

 her input is an nbit string， send it to Bob as a message。

 and then Bob can then determine whether x and Y are equal so that's an endB communication protocol and the theorem is that there's nothing better even if you allow yourself multiple rounds。

 there's nothing better。哎。And now let's use this to show that。Again。

 let's say distinct elements is hard。So。嗯。Falling from this。We already know this。

 we know this be a compression argument， but now we're going to show it using communication complexity。

If a。Is it deterministic？Exact。Algorim。For。Distant dos。Then a uses。At least and bit of memory。

So in July， when you say CC of EQ is greater than or equal to n。

 so what is what does that mean that it's greater than or equal to n？Yeah， in fact， it equals n。

 but when I say CC ofF。I mean， the minimum number of bits。To solve。F via a correct。Deterministic。

Communication protocol。So when I have communication protocol。

 I mean Alice and Bob agree ahead of time on what their protocol is for communicating like Alice will tell will tell Bob okay。

 like if I get this input。And you know these are this is the message I'll send as my first message and if you send such such as your response this is how I'll respond to that et cea。

 they basically know the protocol the only thing that they don't know is what each other's inputs are okay got it and then。

Yeah。😊，Is the number bits transmitted that's right， numberumb bits transmitted got it， okay。

 transmitted。What is M here， the theorem？Oh， there is， yeah， there is no end。And。And as the。

The universe size for distinct elements。Thank you。So， I mean。

 the proof is going to look very similar to what you saw before。 Actually， in fact。

 let me just be a little more。呃。I I think that's， yeah， we can get into this， so let's prove this。

So here's Alice。Here's， Bob。Bob has some Y， which is in zero1 to the n。

But you can interpret that as like it's a subset of one to M in the usual way。

 one means that the elements in a set is your means it's not Similarlyly， Alice has some X。

Wehich should can it as a subset。And then Alice runs the streaming algorithm。On。The elements of x。

In sorted order。Then， sons。The memory contents。Of a。To Bob。As a message。说的是。嗯。Well。

The number of bits sent is equal to the space usage of a， right。And then。

 Bob can now continue running。Well， first of all。Let me do one thing first。

The first thing Bob does is。First， computes。Let's call it T。Which is A query。

Which is just going to equal the size of x， right？So the first key checks is do x and Y have the same size？

Okay， if they're equal sets， they'd better have the same size if the size are not equal。

 you can already you can already reject and say no， these are not equal equal strings or equal sets。

嗯。And。Outputs， let's say faults。If T is not equal to the size of y。Okay， and then otherwise。

Bob continues。running。11 news running。Scrip A on the elements of why。And then。He calls。

Adoc query again。RightAnd one or two things will happen。If x and y are equal。Then。

This will just be the size of y again， right You won't have added any new distinct elements if x and y are not equal。

Because you know they're the same size， you know that there's something。

 you know why can't be a subset of x if they're a strict subset of x if they're the same size and different。

So y must have an element that's not an X。Therefore。

 the number of distinct elements will have gone up and it'll be bigger than the size of y。

 which is the same as the size of x。So， if。T is equal to the size of y。You know， output。True。

Otherwise。Ill put falses。好嘅。😊，Does that make sense？So。一子。😊，嗯。And you could ask now。

 what about you know， the randomized so you know at the end of the day？

re the algorithms that we use for distinct elements and a lot of training problems are actually randomized algorithms。

So。嗯。You can ask the question of， okay， what's the can we prove a lower amount on the complexity of a randomized algorithm。

 even an approximate randomized algorithm for distinct elements？嗯。嗯。And。🤧The answer is， in fact， yes。

Actually， a quick question。 Do we not care because like in our in our reduction in our proof for the。

Like using air correcting codes for the for the randomized variant like it required the decoder required us to do this exponential search so do we not care about like the runtime that Bob and Alice。

Use like in this protocol like we don't care about like possibly having Bob look at like an exponential family of subsets。

 Yeah， we don't care about running that's right in communication complexity。

 we don't charge people for computation All and Bob internally on their sides。

Alice might be solving the halting problem for all I know to determine what message she sends that's completely loud。

Great， thanks。Yeah。嗯。And okay， so actually， let me just let's I just want to say a couple more words about equality。

You can look at， for example， the randomized。Let's say the randomized。Public coin。

Complexity in the one way model。 So this arrow means there's only one direction of communication Alice talks to Bob and and Bob doesn't talk back。

 So in other words， since there's no conversation Alice might as well send your entire message is all up front So there's only one message ever Alice talks Bob here's that message they share a public common string Bob has to output the answer and let's say you want to fail with probability at almost a third。

Forty quality。首这是。The minimum cost I don't know why my I should probably。

Fix this and let's say lock the screen。Okay。So this R pub arrow 1 third means。😡。

I want to have a public coin randomized protocol， which fails the probability at most a third for equality where there's one message only from Alice to Bob。

And I want to know， what's the cost in transmitted bits？Of the best protocol。

 communication protocol that can achieve this。And any guesses。

 so we know deterministically you can't do better than end bits。

 which is completely trivial Alice can send everything， what do you think you can do in this model。

With public randomness grant， you， with probability a third。Any guesses？Close to like theta of n。

Da event， so it's still basically maybe a better constant， but still linear。Yeah。Any other guesses？

But yeah the， the input I made right we' still doing like whole input， yeah。嗯。So I'll just tell you。

 yeah， yes， I guess I think if we feel like it it should just be， yeah， it's just be。

So the answer is that's actually constant， okay。And the idea is， you know， Alice。

 so there's this X that Alice has， which is。It's an endbit string and this is why that Bob has。

That's say equals that n element equals。And what they're going to do is there are these public random strings in the sky。

 right， so they're going to interpret that as like。So let's say there's。

 there's just a bunch of bits in the sky that everyone can see。

What they're going to do is they're going to take the first end bits。

And they're going to call that Z1。We're going to take the next n bits， we're going to call that Z2。

 et cetera。 you have the Z2。And。What Alice is going to do is going to send。X。没有时间。

She's going to send a bunch of doc products。X dot Z1， mod 2。X dot Z2。马超。And then x dot Z。

 let's say R mod 2。And Bob。Checks。Whetherather。Let's say y do zj。Is equal to x dot ZJ。My two。

For all J going from one to R。So if any of those dot products are different。

 then their inputs are definitely different。And any of those。

 but if all the dot products are the same， that doesn't necessarily mean that the vectors are the same because。

 you know， maybe that maybe the Zj just failed to witness the difference， right？

But what does it mean， what does it mean that？Y dot Zj is equal to x do Zj mod2， it means that。

X minus y dot Zj。Is equal to zero material。That's what it means。And if X and Y are different。

Then x minus y is not the zero vector。😡，X not equal to y implies that x minus y is not。

The zero vector。So in other words， x minus y， you know， has， it might have some zeros。

 but then it definitely has a one somewhere。And then it has some other stuff。

 which might be zeros and ones。And then you're dotting it with。You're doting with ZJ。

 which has some stuff here。And then it has something here， which is random。

 and then it has some stuff here。Right。What's the probability that x minus y dot Zj is0 Well。

 none of this matters because it's being dotted with zero。

Let's condition on the doc product between these parts， mod2。

That dot product is either going to be zero or one。

 it doesn't really matter it's going to be something。😡，And whatever it is。

The contribution from this part will flip it with probability a half right it'll keep it the same with probability a half and it'll flip it with a probability a half namely if the question mark is a one it'll flip it if its question mark is a zero it'll keep it the same so it's 5050 switch right。

So， the probability。That。We fail to catch。X different from y is exactly equal to1 over2 to the R。

Because we did it all times。So every single one of those doc products tend to fail to catch it so you know if we're just trying to succeed with probability two thirds。

 in fact you can just pick R to be2 and you to if you want to succeed with probability1 minus delta you can pick R to be log whatever delta。

Okay，Does that make sense？把数。So this doesn't。Seem immediately useful for lower bounds because。

It looks like this communication complexity is as low as you could possibly want it to be。

That's right get to go to private randomness then to get a alert。 So so that's a good point。 So here。

 here， you know， it's a real's。We really gave the All and Bob a lot of power by being able to share this public random string right。

 but if you think about corresponding what does that mean from a streaming perspective if I wanted to run like a reduction。

 if I wanted to like do what I did on the last whiteboard and solve my communication problem using a randomized streaming algorithm。

We've been assuming right when we talked about you know the idealized flly Martin algorithm and distinct elements in the non idealized version。

 one of the components of the non idealized version was look。

We can actually store these random I mean you know we don't actually have these random hash functions for free in the sky whatever hash function we're using。

 we have to store its representation in memory that costs us memory。😡。

So it's a similar phenomenon here look our randomized our randomized streaming algorithm we can't just assume that all its random bits are stored are stored for free in the sky it has to pay to store them so that's more in tune with the or more in line with the private the private model of communication right so you can ask。

What happens there， let's look at our private one way， one third。For equality。Right。

 it's not sinking， is it？咩笑出你啦。

![](img/9bb2c7274eabb1ad9fd7085567c3b272_2.png)

Oh testing， can you hear me？Yeah。hello hello。Yeah， we can hear you。嗯。Yeah。

 I finished it like yesterday。I think there's just some Zoom acted very something's been on with my speaker。

 I can't hear anyone。Can someone， if you can hear me type in the chat oh we can hear you okay。

 for some reason I can't hear you though so。Can someone type in the chat。

 were you also kicked out of Zoom or was it just me， both my devices were kicked out suddenly。

You know what the dot data， dot word and dot text stuff does。Okay right， now I can hear everybody。

 so say that again。Oh just say to think about the four sections of memory， right。



![](img/9bb2c7274eabb1ad9fd7085567c3b272_4.png)

Sorry， I'm just coming back now because for some reason my that's code started deep and snack。But。

I I， I don't think you want to be。And you did are you in a difference in composition。Yeah。

 I think I Sheck has thismic on by accident here， let me let me mute him。No。

 he needed himself looking agree。 sorry sorry about that。 I don't know。

 I had some technical difficulty reing there， but I'm back。So yeah。

 so let's look at the private coin complexity of equality。And any guesses as to what this thing is？

Is this a harder problem so is it is it it is harder right I mean because now they can't they can't assume know each other's randomness if they want to share what random bits they use they have to communicate it。

This seems like it should be N， right， because the thing that are close close to N， right？Good。

 so I'll tell you the answer is actually login， login。And， you know， it's。The诶。你啊。

The lower bound so there's a general theorem that says basically。That the deterministic。

The turbistic complexity of a function is that most something like exponential。

In the private coin version。So you know， we know that。We know that this is at least and right。

 so that implies that。And we know that this is true just from that theorem。

 I'm not going to prove this theorem。But how about the upper bound？

 So this says that there's a lower bound。 How about the upper bound， upper bound。嗯。Alice。

 right again， has X。 Bob has Y。We can treat these number， we can treat these x and y as being。

Numbers。In the range。Zero up to like two to the n minus one right their theyre end bits so we can treat them as numbers that are end bits long。

 so they're up to two to the end。And the point is。Let's look at we going basically what we're going to do is Alice。

Alice will pick。A random prime。皮。In the range。From let's say。1 and cubed。And she'll send her number。

 modp。And then Bob will say yes， say true。If and only if x is congruent to y not p。O。

So she sends the prime as well。Yes， that's right。She says XRP and also sends P。

Right because it's private randomness， so he doesn't know what her key was since he doesn't know her randomness。

the point is now P is at most un cubed， so sending it takes log n bits。

 X mod P is at most P' so sending it takes that most log n three log n bits。

 so altogether we're sending O of log n bits。And the point is， look， if x equals y。

 they'll definitely be equal mod p， if x is not equal to y， then basically if x not equal to y。

Bob is fooled。If and only if。P divides x minus y。唔。

But I don't know if you know this from the prime number of theorem， but like。And has。At most。Oh。

 a log n over log log n。Priate advisors。I mean， this is actually not even the prime number theorem this is just。

Maybe I'll leave this。I'll leave this as an exercise so the fact that a number has at most log end divisors is pretty simple because prime divisors because if you do the prime factorization。

 let's say the primes are P1 up to PK you have that p1 times P2 times p3 dot dot times PK is equal to n you know that each of the PIs is at least two。

So you know that n is at least two to the k therefore k is at most log n so getting a log n bound is not that hard I just I just proved it to you right now。

The log in or log log in bound， basically the ideas。You know that the primes have to be different。

 they can't all be two， so you know that the Ih prime has to be at least I。😡。

So P1 times P2 times that odd times Pk must be at least k factorial。

So you know that n is at least k factorial。And if you just use sterling approximation or even something simpler。

 that implies that K has to be at most oh of login every log login。So the point is。

You know that if x and y are different， x minus y， let's call this number capital n。

X minus y is at most capital N， so it has at most log roughly log of capital N divisors。

So if I pick a random prime as long as I'm picking from a range that has way more than log n primes。

 then I'm golden， the likelihood that I'll pick a prime that's a divisor is small and by the prime number theorem you can say look between one and little n cubed there are a lot of primes。

 there are roughly little N cubed over log n primes in that range by the prime number theorem。

So the probability that I pick a divor is very unlikely。是不对。So， that's that。嗯。Right。Are there it？

Are there problems for which the like this inequality that you wrote in this theorem the communicate like the deterministic communication complexity is less。

 you know， is basically what this says is the private communication complexity is at least logarithmic and the deterministic complexity I there are there problems for which it's actually equal like the the or close to equal that the deterministic problems where both of them are super hard。

 randomandomness doesn't really help you。We'll see one of those soon。

There are even ones where public coin randomness doesn't really help you the public coin so it's not crazy to think that it's not crazy to think that theta of n would be a possible possible band there are problems where that that is true where randomness。

 even public coin randomness doesn't buy you anything。O。

It just just so happens that equality is like the most extreme example where it achieves kind of the biggest gap that's possible。

Okay。So Jone， yes， could you quickly just explain what you're saying in the theorem。

 I don't understand that。In the theorem。Yeah， in the statement of the theorem。Oh。

 so are you talking about this theorem？Yeah。So yeah。

 you can ask yourself the question of what's the biggest possible gap between the deterministic communication complexity of computing a function？

Versus the， the complexity to compute that same function in the private coin setting with a randomized protocol。

 and the gap is always at most an exponential gap。You cannot have more than an exponential gap between these two。

😡，系先。Next slide。And equality is an example where you actually achieve this exponential gap。Okay。

So anyway， let's get back to more streaming lower bounds。So let me actually introduce one where。

I do want to do one at the end where I actually prove the communication lower bounds。

For now'm just I'm just assuming that someone else has proven the communication lower bounds and showing how to use it for streaming lower bounds so one really hard problem kind of a canonical hard problem in communication complexity。

Is what's called disjointness。So here again。I's say they have sets， so LF has a set S。

 which is a subset sort of one to n。Bob has a set。Which is a subset， which T。

There something I want to add。And this jointitness。Applied。To these inputs。Is equal to one。

 if the word is joint， if s intersect t is the empty set。And 0， otherwise， if they're not disint。

And theorem。Is that you know so here's an example so what's the most trivial thing that they could do the most trivial thing is Alice could just simply send her set to Bob which you know just a bit the indicator vector of her set so a one if I is in the set a zero if I is not in the set for I equals one to n that's an end bit message so the absolute trivial protocol is end bits that's the deterministic。

And the theorem is that even。Evenith with public coins。

And even if they're allowed to talk back and forth， it doesn't have to be one way。

The communication complexity of disjointness。Is omega n。

So other than improving the constant factor in the mega。

 if you use a randomized protocol of public randomness。

 you're not going to do better than much better than the tri protocol。

And now let's look at a stream problem。Streaming。You know， we see。

Let's say IY up to like IL and stream。This defines a histogram。X。Where Xi is the number of times。

We saw Is dream。你觉得嗯嗯。So like the streaming question is when someone says query。

I just want to output。The Elinfinity norm。You know， even up to a factor of two。Well。

 that's absolutely a factor of。It's actually  one point， let's say 1。1。So I want to output。六四十五。

Zilda， such that Zilda is guaranteed to the at least afinor。And at most 1。1 times。With probability。

 at least two thirds。切。And the claim。So is's in the number of just some elements here。

N is the universe size， so every integer you're seeing in the stream is coming from the set right up to end。

 so just like distinct elements， n means the same thing。1。1 approximation。呃。嗯，finity。In stream。

With probability at least two/ third。Requires。Oomega n bits。A memory。行。Let's prove it。So。

I's the same thing you're used to， so Alice gets this best。Bob gets his tea。And then， Alice。

Runs the algorithm。On the elements of S。And then sends。The memory of the algorithm。To Bob。And then。

 Bob。Continues。Actually， and Alice should send one more thing too。Actually， that's fine， That's it。

And then Bob continues running。Yeah algorithm。嗯。On the elements of tea。

Then queries then does cause ADdoT query。So the possibilities are STR disjoin。In which case。

Nothing appeared in the stream more than once， so the L infinity norm is。You know。

 it's either zero or one。 zero is trivial。 It means both sets were empty， but， you know。

 it's at most one。Meanwhile， if they're not disjoint， then there's an element that's in both。

 so the unfinnied arm is two。😡，So you're deciding between at most one or equal to two。

 if you have a 1。1 approximation， then that will tell you which one which case you're in。

So you've now used this screening algorithm。To solve disjointness。

The total communication complexity of this protocol is exactly equal to the space usage of A because the only thing you sent was the memory contents of A。

Therefore， the memory has to be at least the disjointness lower bound， which is omega M。Okay。

 does that make sense？It's a little weird that this proof and the other proof both for some reason seem to deteriorate when you get an approximation factor of larger than two。

 is there a reason like a fundamental reason why like 2。0001 is impossible？Yes。

 and actually I'll explain that right now。 So the bottleneck here was that we were looking at two party destroyjo this。

 but you could look at。Tea Party destroyed join this。We， can we get back to the。The previous proof。

 yeah。嗯。Its that that Alan feundy norm， is that just the。

Like the the highest frequency of any element。 That's right。

 which in this case is is either going to be two or one。Wait why。Because you know， S is a set。

 so nothing appears more than once in S set yeah。嗯。

So if Tea Party justjoin this is the following general you know more general problem or generalization。

 basically there's a bunch of players now there's Alice1， there's Alice2 up to Alice T。

Each one has their set， S1， which is a subset of1 to n， S2， which is a subset of  one to n， etc。And。

There are two cases。For your promise that you're in one of these cases， okay。

 that' that's part of the problem definition is this promise。

 your promise that for all I not equal to J， AI intersect AJ is the empty set。Or two。

 you'll promised that for all I not equal to J。AI intersect AJ is equal to。Something， some fixing。对。

So there's either they either have all empty paras intersections or there's like one unique person who's in every intersection。

So it's even a special case， you know， you could just the second item two， you could have just said。

That， you know， they all have something you know， they all have a shared intersection。

 but this is even。I'm promising even more than that and the claim is that even this is hard。

So the theorem。Is that？Our pub。one third。OfI'll call it misjointness。NT。

 meaning that there are T players and thes are subset of one to N。Is mega。Evity。Oh。

 and I should say what the model and you know， let's just actually say in the one way model。

So in the one way model， the you know。The model here is， again。

 there's a public random stream in the sky。Alice one sees her input as well as the public random string and chooses to send one message。

Alice2， then based on that， her input and the renderry sends a second message。E cetera。

 this person sends their message。And then LST sends the answer。

So when I talk about the total bit sent。Is equal to basically the size of M1 plus the size of M2 plus that or that plus the size of M1。

And of course， a corrollary of this。Is that。There exists some player。三定。Omega n over t squared bits。

Right because there are two players， each one sends， you know， in total。

 they're sending innerveree bits， someone has to send at least a one over t fraction of that or one over t minus one fraction of that。

 which is omega inner t squared。对。So。Was does this already tell you。

 This tells you so a quarollary of that。Is that。律史上。I guess is it alpha approximation？So if you have。

So here's what I want to say。嗯。If in the disjointness case。

 in the case then they're actually disjoint。You know you can imagine running a stream on this right where let's say it's a streaming algorithm that approximates the L infinity norm。

 Alice runs it on her part， sends the memory contents to Alice2， who runs it on her part。

 sends it to Alice3， et ceter。In the case where they're all dis joint。

 the Lfinity norm is going to be one。In the case where there's someone who's in all the parawise intersections。

 so who's in all of them， then that person's that person is going to have an。

A weight of T right so you're basically if you can if you have an approximation factor in your algorithm that's T。

 you can distinguish between case one and case two。对。So。And you know that know what's the memory？

You know that you need you know that in such a case some player had to send at least N overRT squared bits。

 but every player is sending the same number of bits which is just the memory contents of a so you know the memory has to be at least an overt squared so what this says is if you have an alpha approximation that implies that you need an over alpha squared memory。

对。So this is， yeah， so this is what this is an example where you're not， you know， you're not。

Bottleneck to by an approximation factor of two you can get better you can get a hardness even for larger approximation ratios by the way。

 you I mean I know it's so it's it'sta theta of t but you actually really only need an approximation that's like t minus one over two。

 right？Yeah， something on or something or not not not not it's not going to be t -1 over two it's going to be like the right multiplicative thing right it's like going to be T over two or something if I say like this Yeah most alpha times the Ly norm。

And that at least the yellow footty or， yeah then you don't even need to divide by two。Yeah。Okay。

 one more thing that I'll discuss before I move into actually proving giving you a proof of a communication lower bound。

Ly， I have a question in the chat。Okay， we looks good。U。Yeah， so what about estimating the LP norm？

It's say the LP norm。For 1。1， let's say。No it doesn't really matter that much。Remember。

 the LP normal vector is just defined to be the sum of  Xi to the P all to the one P。

's this is a norm for a P that's at least one。Sorry。

 July one question about the last thing we just discussed I was just thinking do we so what we just said is that if we have a random eye if we have a。

Right， so are any randomized。Algorithm for。For computing distinct elements or like this L infinity distinct elements yeah infinity there's no distinct out that justity yeah yeah yeah。

 L infinity。It requires an over alpha squared memory did we did but what what like do we know from an upper like what algorithms actually do we know for this setting if you think of alpha as being a constant。

 then this is really bad right this is saying yeah want a oneceptpsilon approximation。

 which is the kind of thing we've been doing so far。

Then it's basically saying that there's nothing non trivialvi right right so yeah。

 so this is kind of a big a big doubter。Okay， got you。嗯，OK。So。Yeah。

 in terms of actually achieving this N alphapha squared。

 I guess we'll see about that later that there's something you know what can you do。

 how do you achieve N alpha squared if you wanted to， for example？we have not covered that。

Was that was saying there's like nothing non trivial for。Elanfininityino him。Sorry I said again。

Right so what was the previous results say that there's like nothing non trivialvi for that essentially right if you want a constant factor approximation。

 it's saying that there's nothing nontri I mean you know。

 definitely you can't do better than than shaming a constant factor。

 you have to be linear and add in your memory。嗯这。No I' been like a happy hits thing from 170。

 is that like not the same？😊，Oh， it just tells you what the idols and tell you how frequently the APA Oh no。

 well we' we're going to talk about Henry hiters in this course。

 but it's not it's it's a weaker guaranteed on Ellen Kennedy。We'll get there。 We'll get there。对。

So what if I want to estimate maybe the LP norm？So， you know， what I could do is， you know。

 in case one where they're just joint， you know that the LP norm。

's let's just raise it to the P of power。Is the sum of X to the P？Is at most n？

Because each one of these X's is either zero or one。So when you raise the P， it's still  zero1。

 there are n of them。Meanwhile， in case two， you know that。

There's some guy who appears at least t times， so this is certainly at least T to the P。

So if you imagine， you can set notes， so let's set T。To be something like3 n to the1 over key。Okay。

Then。This step would be bigger than。对演。So there's a constant factor gap there。

So that implies theorem。You know，1。1 approximation。呃LP。In a stream。

With a randomized algorithm that succeeds with probably at least two/ third。Requires。

Omega n divided by t squared， so that's basically n to the 1 minus 2 over p。It's a memory。So this is。

 you know。难需要。Not true， Not truly large。For any P， which is strictly bigger than two。

And it turns out this is tight。Maybe surprisingly， In of Woodruff。In 0，5。Show an algorithm。Achieving。

You know。Polly went over epsilon times， Oilda， Otilda's hiding log n factors and the1 minus2 over repeat memory。

For one plus upon approximation。So somehow this magic exponent is exactly the right answer。

Up to life factors。Why do we get to decide that t equals ceiling of three n to the one another P because we get we get to decide which remember how do we show hardness of the streaming problem。

 we reduce from a hard problem， right？And we get to choose which hard problem we reduce from。

So let's reduce from the disjointness and T problem where T is this。呃嗯。Okay。So。

 so now enough enough of taking。Communication water bounds for granted and using them。

 let's see how you can actually prove a communication water bound。

So proving a communication loweraround。So。嗯。What I'm going to show you is that there's a problem that's called。

Indexing。In fact， even a version called augmented indexing。I'm going to show you that this is hard。

Okay， we're going to improve that。And then we to that this reduces to a problem。Called Gap Hemming。

Therefore， gap havingm must be hard and gapham reduces to。Let's say one plus epsilon approximation。

Of distinct elements。Therefore， one plus epsilon approximation of justda elements must be hard and in particular。

 we're going to get out of this in omega1 over Epsilon squared bit lower bound。

For one pluspsilon approximation of distinct elements， which is actually the right answer。

You can achieve10son square bits， so the right answer is10son squared plus log end bits。一是要求不要。看。So。

😊，嗯。Maybe I'll do this in。Reverse order， so I'll define what these problems are。

And then I'll show the reductions in reverse order and finally show that augmented indexing is hard。

Okay， so。So what are these problems so indexing。Alice。Gets a subset S of one to N。Bob。

You get an index I between1 and n。And there's only one message sent from us to Bob。

 so it's one way communication。And indexing。S I comma I is equal to SM。Or actually。

 let's put's the safety rate。Is it more convenient to write this as a string？

So let's say this is x and 01 to N。So。It's just the I bit of X。So it's intuitively。

 and let's say there's public randomness。Intuitively look。

 there's only one message that Alice is sending Alice has no idea what index Bob is holding right so what I mean what can Alice really do other than send her entire string to Bob。

O。And in fact， that is true。The theorem。Is that？Our pub in the one way model with probability。

 let's say failure probability Delta。Of。Of index。Is at least it's omega n， in fact。

 it's this one minus binary entropy function applied to delta times n。

And if you haven't seen this H2， the binary injury function applied to P。It。

Minus is let's say minus P log P。Minus1 minus P log，1 minus P。I mean you can plot it。's say this is。

I mean， it only makes sense when keys between 0 and 1。 So here's0， here's  one， here's a half。

This kind of looks like this。Yeah。Good， so if you think of in know， so in particular， this is always。

There's always at least aomega end no matter what else it is。

For for any Dlta less than a half is at least so again。嗯。So something。

 isnsn't this a little funky because like。If I take the。Like if I take Delta。

 so Delta is the failure probability， right？And like。

If I fail like if I want that failure probability to be small， I would right。

 I would expect that this thing would get closer to n and that's that's that's what happens right right。

 but then but it goes but but on both sides though， right of one half。Yeah， but this。

This theorem assumes that， I mean， it delta so。This theorem is assuming that Delta is at most to half。

So I should have put this here。If D says at least a half。

 this is completely a trivial problem because。If I'm willing to fail it probability I have。Bob。

 we can just flip a cold Oh these are binary strings， right， So it's not Yeah， Okay， yeah， yeah。

 yeah， Okay， fine。 Okay， Got it。So this is the indexing problem。 Yeah， yeah， yeah， Okay gap having。

Alice and Bob again get some strings of input。And they're promised're one of two cases。Either。

The having distance， we talked about having distance when we talked about error cring codes。

 just the number of entries where they're different。

You're told that either the Haming distance is at least n over two。

Plus red n or the having distance is at most and over2 minus red n。And you have to decide which。

In a theorem。Is that。A pub。Of this thing。Is also omega n or omega yeah， omega n。对。

So that is that clear in terms of the？IIs there a reason for this plus minus rooton window that we're looking at？

Yes。You mean as opposed to simply determining whether it's like I could take yeah。

 I could take it to be just some epsilon right like and over to plus minus epsilon。

 but why do we take it to be。Like what is so special about Ruen？Yeah， so I guess you'll， well。

 I'll prove to you that it's hard， so you'll you'll see in the proof where that comes up。

We're going to make use of that rootin。We're going to make use of the definition of the problem when we prove that it's hard and that Ru end is going to play a role。

对。Good， so let's now move to reductions。So remember the picture I said that we have indexing。

Reduces to cap canning。Rduces to。One plus Epsilon approximation。I distinct elements。So。

 so now we're going to show that。嗯。Gap timing is hard。Implies that distinct elements is hard。

So we're doing reduction so take。A gapap， how instance？With strings。Of length。W of rhpson squared。

We know that therefore the complexity。But that problem is oh a want to rope on screen， right。

That's what we said on the last slide。It's omega， the vectortro length。So now。Alice runs。

 it's the same story as usual Alice runs， so now let's say that we have a really good streaming algorithm which provides a one plus epsilon of approximation。

Alice runs that algorithm。う嗯。On。The I such that X is equal to1。And then sends the memory。怎么的。

Bob continues running。嗯。On the eye such that Y I is one。And actually， let's also send。

So sends the memory of Bob。As well as sends two things。

 the other thing she sends is the support size of x， the number ones。So。Alice's message。Is。

Or her message length。Is what's the support size， it's a number between zero and one over epsilon squared because the length of x is one of epson squared so writing that telling me which number is takes log of one over epsilon bits or log of one of epsilon squared bits。

 which is the same as two log1 over epsilon。So analysis message length is。At most。You know。

 too long whenever uppsilon。Plus。Mm a bits。And then I'm going to show you that you can use this message to solve gap haming。

 We know that gap haming requires omega what rhpson squared， so that will imply that。

M a the length of the memory of a is at least this omega order epsilon squared minus two log1 epsilon。

 but of course log1 epsilon is much much smaller than polyone rhpsilon it's much less than one rhpsilon squared。

 so this is omega1 epsilon squared。Does that make sense。That's where the Lord God is coming from。嗯嗯。

嗯。And。Yeah， I mean， I guess the point here is。For us。嗯。This additive root end。

 right you're basically you basically have to decide a difference in terms of and you have to decide a difference of an additive root end in the handlinging distance。

喂。And the point is just。If n is what our rhpsilon squared。Then you know root end is one over epsilon。

 so basically。The idea here is just。If n is1 of epsilon squared， then rootta n is equal to1 of epson。

 which is the same thing as epsilon n。Right so if you're able to determine the hamming distance。

Up to an additive Epsilon N。basically the idea is， look， if I can solve distinct elements。

 I can use that to determine an additive whatever epsilon and decide the difference between these two cases。

Does that so back to your question about why the root end does that does that answer your question that like yeah yeah okay。

可以。So I I think I don't have a whole lot of time left。

 So I'll just assert and you can check the notes。 I'll just assert。

Check minutes if you want that the one plus epsilon approximation。A distinct elements。

We'll let you decide。The having distance up to additive。

One of Rulands is exactly what you're trying to do here。

And now let's try to prove that gap having is hard based on indexing。So this is what I said before。

So proof。What was our a bound for for index Again mean can you it was and right yeah okay。So。嗯。

Let's do the following， so。Basically， I'm starting off。I'm starting off with an innote。

 so I need to show because I'm going to reduce indexing。To gap hand， right？So what does that mean。

 Alice？Has an X。Bob has an index。And Bob wants to know what is XI？So here's what we're going to do。嗯。

Or you can think of it as。Bob has。know Bobb has， let's say some e i。We eyes。

 know eyes and when to end， right？EI is the I standard basis vector。In theI position。

And what they want to know is the dot product。对。Check there。So。

They're going to use public randomness here。😡，And first of all。うん。

Alice is going to convert her string into。Some x prime， which is in。us1。诶。one to the end。Where。

X i is plus one。Means X I prime is -1。And X I is 0。Means X prime is plus one。

So she's going to interpret zeros as ones and ones as minus ones and convert her binary string01 to the n into a minus one1 to the end string。

Then the public randomness。嗯。Let's say that I'm doing。嗯。Gap hamming on strings of， let me。

 because there are two different ends here。 those for indexing gapming。 So let's say that。

Gap having on Capital Mbit swings。Is there a couple then。And now。

I want to solve indexing on a little M string。And we're going to reduce that to that Hamiltonon a capital end stringing and capital n is going be it's going to be theta little n。

Okay， so。Good， where was I。 So public randomness。They're going to in the sky。

 they have this randomness that's going to specify some R1。Which ist minus 11 to the n。Or two。

 which is in minus1，1 to the n。All the way up to our capital L。Rs the -11 to the end。And then。Alice。

Is going to turn。X prime into。嗯。The vector with all these different dot products。X prime dot with R1。

X prime do with R2。X prime down with RN。And then Bob is going to do the same thing， he has EI。

He's going to turn that into。EI dotted with R1。EI do with R2。He eyed out with RM。By the way。

 of course this is just， of course， the ifF entry of R1， this is just the ifF entry of R2， etter。

And the claim is that。You know， so now theyre there are these two strings。 Let's let's say。

 let's call this string。We have the names。This is string A and B。Okay。And these are。Celend strings。

That actually really just made sure I'm。I should have put the sign of this。 So all these are signs。

这是个啥。All these are the sign of the dot product。And you know， just so I don't have to worry about。

Just so I don't have to worry about like what if the dot product is zero， I'm going to say that。

And here was odd。I'm going to reduce from indexing where little L is odd that way the dot product is never going to be zero。

And the claim is that if I can solve gap counting between little A and little B with high probability。

 that's going to let me recover。The solution to indexing。好。😊，So let's keep going。So。Yeah。

What does Bob have in his hands now？Bob has this B， which is in minus1 to1 to the n。

 and B is equal to。The ice bit。I think you want capital N， right？Yes。The ice bit of R2。Yeah。

 I that of。Our Cha1。And we're looking at the haming distance between this and what Alices has。

She has her little A。And A is all these signs of dot products。So， sign。Let's call it。嗯。R1。

R 1 I X prime I。Plus。The sum over J not equal to I of that dot product。So R1 J dot of x prime J。

The sign of。All right， two x prime I plus that sum of J not equal to I of， et cea。唔该。So。

Let's look at this。What is？And what is the distribution of this？你谁。So remember。

 I said that little N is odd。So here we're summ over all the indices except for I。

 so that's an even number of indices。Right。So we have a dot product of an even number of terms here。

And you know， it's a symmetric random variable right， you know。

 just it's just as likely for this sum to be L as it is for it to be minus L。Because in particular。

 if you have some configuration r of RJs that give you L。

 it's equally likely that you got the negative of all those RJs and then you get minus L。喂。So。嗯。

Conditioned。On not being 0。嗯。Plus， minus are equally likely。And furthermore。

 since there's an even number of terms here。嗯。The sum has to be even。

Does that make sense're actually because each term that you're adding is odd it's either plus one or minus one it's odd。

 you're adding an even number of odd things so the sum has to be even。

So not only is it equally likely to be plus or minus， but。Whatever it is， if it's not zero。

 it's at least two in magnitude。😡，Meanwhile， this part here。Is equal to one in magnitude。

So if that black circle is not zero， then whatever sign it has will determine the sign of the whole thing。

ok。😊，Only when that black sum is zero， does that yellow part even matter？Does that make sense？Yeah。

 yeah， okay， good。So。😊，And。😊，So let's focus on that。

 let's say that the sum in the black circle is zero。Then what can we say about the yellow part？

If the black circle is zero。Then there are two cases。

 either Xi prime is plus1 or Xi prime is minus one。

Remember now comparing we're comparing that yellow circle with this yellow circle because we're looking at hamming distance so the question is are these two things going the same or different？

If Xon prime is1， it's going to keep it the same。😡，If Xi prime is minus1， it's going to flip it。

Right so basically， you can think that if you compare if you compare now， let me put it in red。

 if you compare this entry。With this entry。Kind of most of the time is just randomly equal or randomly different or randomly different 50。

50 like basically as long as the black sum is not zero， it's just 50，50 different or same。

 but in that small percentage of the time where the black sum is exactly zero， I either bias myself。

To equal the entry of B or I bias myself to be different from the entry of B based on whether X I prime is equal to plus1 or minus1。

 which basically is the same as based on whether X I is equal to zero or one So whether or not the bit whether or not that bit。

😡，That I bit of x was01 will introduce a bias one way or the other。😡，Okay。

 and sterling approximation。可以。😊，what is this black circle that it equals zero？Basically。You know。

 the amount of。I mean it depends on exactly well let's just you know let's consider the case where all the xjs there are ones you know every other case are is basically this is going to follow the same kind of argument if all the xjs are one。

 then for that black sum to be zero exactly half of my RJs have to be one and exactly half of them have to be minus one and you can ask so what's the probability of that the probability of that is roughly。

And choose。N choose n over two。Divided by2 to the n because the total number of rs is2 to the n。

 the total number of R's that have exactly half of their bits as plus one is entriess n over 2。

 and Sterling says that this is roughly one of a root end。ok。So I'm basically either biasing myself。

I'm biasing so either。Those circled rabbits。Are equal。With probability， about half plus one root end。

Or any。With probably， roughly post one。So I'm biasing them by this one of root end。

And then if you repeat this many times， kind of an expectation。So， an expectation。Glanni。

 should that be one one half my minus one over group Well， I said unequal the probability， yeah。

 so if I had if I had said equal， then I agree with you if I had said equal。

That would be half strong。So they're either equal to probably have plus1 over root n or1 half minus1 over root n。

 sorry， the reason I've put them both plus before because one of them said unequal。Okay， good。

 so an expectation， kind of the expectation of the heming distance。Between A and B。Is either。

N over 2 minus redn or n over 2 plus red。Or not capital N。I should actually say differently。

Capital N over little end。Capital Ed over。Does that make sense。

So if I pick something like capital N to be， I don't know， 1 or10 of 10 end or something。

Or actually then I to put 10， but give me something under nine end。嗯。想话大。So。Yeah。

 it doesn't matter so much， but I mean the point is then I can say that。嗯。

So then this becomes basically capital n over nine， this becomes capital n over9。

 so then it's like n over two。Plus or minus is basically you know three root n or something in expectation。

 it's either n over  two plus three root n or N over2 minus three root n。

And then I could apply turn off to say that。My deviation。

 turndown will imply that the deviation from the expectation。

Is also on the order of root end with high probability。So therefore。

 the gap will be either n over 2 plus root n or N over 2 minus rooted。Does that make sense？

So this is all just an expectation。So what's the probability that the having distance deviates on its expectation？

Byuy more than， let's say。You know， then。This is at most something might turn off。

So that'll that'll say that I deviate if I deviate know so with high probability。

 I'm not going to give even more than root of capital N so。

Instead I've got a root two plusul minus three root n， not saying root2 plus minus two root n。

 but I still have that root end gap， that root capital end gap。Okay， so that's basically it。

And then I think I only have about three minutes left I do want to say something about the Lagon for indexing。

Questions about this before I talk about indexing。Wait。

 so just to be clear the point is that like if you're biased above n over to。

 so if you're like n over to plus like root n or plus2 root n。

 then that's the same as having X is equal to。Plus one， which means xi is equal to zero。That's right。

 Okay， got it， thanks。Yeah， so。No know whether or not X is one or zero is going to affect whether or not the bias is going to be kind of a half plus root n or half minus root n or half plus whatever root end bias versus a half minus whatever root end bias。

 which which ultimately with high probability will。

The effect will affect the ham distance between A and B。

And it'll be in what the having distance will high probability be in one of these two regimes。

So if my algorithm can tell me， if my communication protocol for gap panning can tell me which regime you might be in。

I then know what the bias was， and then therefore I know what the I bit of X was。hy is it bias it。

唔使去。W why what's， what's making them more or less likely to be equal。Yeah。

 so the point is right right here in this yellow circle right here， yeah。If Xi prime is minus1。Yeah。

 that that biases me for each entry of A to be slightly。

 it's slightly more likely that that entry does not equal the corresponding entry in B。喂。

Like if this part， if this part we're not here at all。Then what's the probability that a1 equals B1。

 it's 5050， right？Because it doesn't even matter what B1 is。

 A1 is one half the time and it's minus one half the time。Right。Does that make sense？

Like this black I， I thought， I thought that had to be even Yeah， but this this black circle here。Is。

I mean， sometimes it's zero。But you know， let's if you ignore the times when it's zero。

It's either positive or negative and it's positive half the time and it's negative half the time。

Okay， and so kind of the sign of it is plus one half the time and minus one half the time。

 it's not affected at all by by RI。Right。Yeah， so okay。

 so this kind of this is not biased it's just basically contributing one to the having distance at the time and it's contributing zero to the having distance half the time。

Yeah， okay。Okay， but then there there is some chance that that black circle is zero。

 it was that black circle is zero， the part that I circled in yellow comes into play and introduces some bias one way or the other。

Yeah。And if XI is one。It's biasing it to， you know。

 then that means that that yellow part is always going to be equal to the B to B1。

So it's going to bias me toward being equal to B1， whereas if X prime is minus1。

 it's going to bias me to be different from B1。And by stling this part here。

 I know that the bias that's being introduced is on the order of whatever root end。😡。

In terms of the probabilistic bias。Yeah。Okay， or if I do I write it this way。

 what's the probability that a1 is equal to B1？Let me call this term， let me just call these terms。

 you know。This part is capital A， and this part is capital B。This equal to the probability。

Now a1 is equal to B1， given that b is not zero times the probability that b is not zero。Plus。

 the probability that a1 is equal to be 1， given that b is0 times the probability that b is0。唔且。

And the point is。This part here， the probability， given that B is equal to 0。

The problem that a1 is equal to b1 is exactly equal to a half， exactly that。

And what's the problem that B is not equal to zero， it's roughly。嗯。1 minus1 over root M。

What's it part that B equals zero？That's roughly what overrun。

What's the probability that a1 is equal to B1， given that B is0， okay， this is either。1。

If Xi prime is equal to 1 or it's 0， if Xi prime is equal to minus1。Does that make sense？Yeah。

 so this is the calculation that I was doing。对。嗯。I think I'm okay， so i'm actually out of time。

 so I think what i'm going to do is。I'll just you know the notes。

 the proof that indexing is hard will be in the notes。🤧嗯。

You can take a look at that and then Monday we're going to get started on what I told you we werere going to get started on。

 which was if we didn't get to。Which is。Where is that。Turn style model， I do want to talk about that。

 so we're going to start that on Monday， so any other questions before we wrap up for today。

Is this proof is in the notes for it。Yeah， the notes for today have not been uploaded yet。

 but they will be uploaded soon and this will be in there。O， thank you。ok。

 so I'll see you all Monday。

![](img/9bb2c7274eabb1ad9fd7085567c3b272_6.png)

Thanks， professorfessor。