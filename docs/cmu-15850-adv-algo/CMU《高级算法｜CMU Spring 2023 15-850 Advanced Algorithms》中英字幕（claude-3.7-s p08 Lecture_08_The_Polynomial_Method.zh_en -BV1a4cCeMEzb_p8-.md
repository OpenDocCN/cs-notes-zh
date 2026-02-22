# CMU《高级算法｜CMU Spring 2023 15-850 Advanced Algorithms》中英字幕（claude-3.7-s p08 Lecture_08_The_Polynomial_Method.zh_en -BV1a4cCeMEzb_p8-

Were talking about matching syn graphs。And you guys remember the basic definitions。

 I'm given a graph。😊，Undirected today， it might be weighted。Waited it allowed。

 we'll see how things go。And the matching if no two edges in the match in this set and share a common endpoint。

We talked about maximum guardinality matching today we'll also talk about maximum weight matchings。

 but it's an actual thing， so weight of a matching。😊，Is just。

You sum over all the edges in the matching of the weight of the edge。Yeah。啊。

We talked about this idea of perfect matchings， perfect matchings are matchings whose size is exactly the size of the graph divided by two。

😊，That is every vertex of the graph is matched by this matching。And。Here's a fact。

If you know how to find maximum cardinality matchings， you know how to find perfect matching。

Because you can just find a maximum cardinality matching if it matches everybody。

 it's the perfect matching。😊，Otherwise there isn't a perfect matching。

 it goes the other way as well if you know how to find perfect matchings and graphs。

 you can find maximum guardinity matchings。😊，Okay， if you haven't thought about it。

 it's worth thinking about， maybe think about it later on。😊，嗯。

So I'm going to be talking today about perfect matchings。

 basically almost all my algorithms are going to be related to perfect matchings and by this claim that I just said since you can find perfect matchings。

 you can find maximum cardinality matchings。😊，Per matchings also come in many different guises。

 you can talk about max weight matchings， min weight matchings， all kinds of stuff。😊，Yeah， good。嗯。

Last time we saw how to find max cardinality matchings and we saw the for bipartite graph。

 we saw things were easier and we saw cuning theorems。And for non bipart。

so we'll talk about bipartitegraphs， we'll talk about non bipartitegraphs。

When I say non bipartite I really mean general graphs。

 I really mean non necessarily bipartite graphs。Bypartite graphs。

 we saw an algorithm that ran in essentially order random and time。

 we said way do things are possible， we didn't really talk about it， not bipartite graphs。

 we saw an algorithm that that you can implement very easily in m and squared time。😊，Well。

 actually we saw the basics of the algorithm， I didn't give you the details of how to find a blossom。

😊，But you can read it， it's not difficult， it's the same idea as how to find an augmenting path。

And what these things have been improved substantially I'm not again going to talk about runtime well I am going to talk about runtime but I'm not going to obsess about the fastest runtime right now。

😊，Good。Last time I had mentioned this， maybe it was a little confusing because I didn't emphasize it enough。

 the best runtime right now is m to the one plus little low of one。😊。

And so you know earlier my little os weren't very clear this is a little of one so it's really very close to linear best known by quaite is m square root。

😊，That's the state of the item。Okay， today we're going to use the linear algebraic approach to find matching and if you haven't seen this before this is one of the classics。

😊，One of my favorite topics。Yeah。And the the idea goes back to。Lazi Los。

who was pointing out that you know randomization is an important idea that we should use in algorithm design。

 I urge you to read the paper I've linked to the paper from the course webage。

 I urge you to read the paper it is like a beautiful paper how we should all write papers。😊。

So Lobus used this idea to exhibit algorithms to find both bipartite and non bipartite matching。😊，嗯。

And then this idea caught。So caught the attention of people who tried to use this to find matchings in parallel。

 and maybe this will be just a very quick discussion of the parallel model of computation。

 which I'm not going talk much about， but at least maybe a lecture or two。Good。So we want to find。

 okay。So。First stop。And tell you a little bit。Okay。

About the main tool that we'll be using and the actual algorithm for today is not the most important thing。

 it' it's this tool that I'm going to tell you。😊，So the the main the。

Herear are them that I' will be using all the time。

 and this is the basis of an idea called the polynomial method。😊，So maybe even before I write this。

 I want to be talking about polynomials， so I might be talking about univate polynomials of the form。

 let's say 3 x squared minus 7 x plus5 let's univate polynomial I might be talking about multivariate polynomial so I'll actually say p of x and after some time I'll stop writing the bar as well so it will be p of x again which won be 3 x1 x2 plus 7 x1 squared minus9 x2 plus。

😊，Yeah， we can could you give us schedule like how to go。

So how do I go from perfect match matching to max cardinality？😊，Let's consider the following。

So suppose I just want to figure out whether there is the first ingredient。😊。

I want to figure out whether there is the perfect matching of size sorry。I want to find。

Whether there is a matching of size。At least K in a graph。So what I can do is I can say， well。

 actually， so I want to find whether the question is does there exist？Of matchingching。Off size。嗯。

At least okay。Okay， so I want to find such an object in this graph。So what I could try to do。

If I could try to add in。哦。And minus K vertic Cs out here。Which are attached to。Everybody。

And also maybe attached to each other。And I ask， is there a perfect matching in this graph？😊。

So the only way to sort if I want to find a perfect matching。

 so maybe I'm saying does that exist a matching of size that least scale over two or something like this？

So these K over to matching edges must match K verticCs out here。

The remaining can be matchshed out here。Yes。So if this says yes。

 then you know at least K ver feess must be matched internally out here。

 and so they must be matching access。😊，So I'm being a little sloppy out here。

 I'm not completely pining down details， but you get the general idea。😊，对。Good。

 so max cardinality matching reducible to the perfect matching。

 so I'm trying to find perfect matchings， but I'm first taking a digression。😊。

And I'm talking about polynomials。😊，Because they'll be the star of today's lecture。😊，Polynomials。

 univate polynomials， multivariate polynomials。Basic theorem of polynoials。A uniate。Polynomial。嗯。

Which is not the zero polynomin。As oh at most。How many routes？So suppose the polynomial has。Bre。Okay。

So I'm talking about uniate polynomial。😊，which is not zero， has at most how many roots。

 the degree menu roots。And let's say I'm fixing some field， you know， over some few。For now。

 you know， think of your favorite field， the real rationals。嗯。Yeah， some prime power field。我带俾我的。对。😊。

Basic fact you know， a line can cross the x axis at most once， a quadratic can do it at most twice。

 maybe zero times or whatever。😊，系。Good。U。Question。Suppose I gave you a polynomial like this。

How many roots can it have？Was that infinitely many？😊，喂。You know。

 a polynomial like this could have infinitely many roots， I could just say。😊，嗯，哎呀。P you of x1 x2。

Its just x1。So if I say x1 to0 and x2 to any value， it's still zero。

 I mean basically I'm not saying anything smart okay。😊，But。Here is the theorem that I can say。

 and this is actually an interesting theorem。I mean。

 this one's also very interesting and the next theorem is going to be a consequence is going to use this。

😊，嗯。Suppose P be an n variant。Dgree。Det。F on that。哎。😊，So P， the nvari degree d polynomial， this is a。

Very know n equals two。呃，Maybe。Okay， n equals  two degree4 polynomial because look at any of these monomials。

And sum of the degrees of the variables out there。That' is your degree of the poly So this is Nvari degree D polym。

Okay。So now I can ask。嗯。No， I see。嗯。Fix。A set S， which is a subset of the。That I'm talking about。

Okay。😊，So now I can ask the question， well， how many routes？Well what is the size of the set？嗯。Of x。

Which belongs to so x is a vector。X belongs to S to the n。I'm choosing each one of the variables。

 the values of the variables from this set。😊，Such that p of x degree equal with  zero。

 so I'm looking at the roots。And I'm saying how many of these elements of S to theN can be roots。对。

I want an upper bound on this。And the theorem says this is atmost B。

Times you decide the best to be animal as well。哎。😊，Special case n equals one。

Then this tiem is the same as that。the differenceYeah， just which side of the bed I woke。哎呀。Yeah。

 no it's yeah， let me just stick with this。Okay。😊，So this says that in fact。

 you know here's a different way of writing it， so I'll say I'm going to take I'm going to actually choose the value of x1 from the set s。

 the value of x2 from the set S and so on so forth。😊，So I'm choosing X。

Uniformly at random from the set S to the N。And I'm asking， what is the probability？

That I hit a root。And I'm saying this is at mostlyly over the cybercases。

ThisThis is the same thing I'm just rewriting。I took this polynomial。

 I said I choose that value of x1 uniformly at random from S。

 x2 uniformly at random from S independently。😊，And I'm asking when do I hit a root。

 I hit a root only with probability D over the size of that。Does this make sense？Yeah。So by the way。

 this this here， this theorem is called the。Shorts。直播。来吗？

The best theorems are called les also actually turned out that this was also proved。😊，By地meello。

And lift。And。And then once you get into these things， it gets complicated， you know。

 people proved it in various little forms and stuff like that， but most people know it as short zip。

😊，Life's not fair。嗯。And this is the tale。Okay， so be happy with the Ta。

Are we missing something hereonent？So because I'm choosing a probability。

 so I'm basically saying I'm going to divide this by size of S to theN。And yeah， I mean。

 it is surprising that there's no dependence on hand out there， but yes。😊，But these two things are。

 yeah。이股乱下。Okay。😊，We good， we good。そてるね。The proof is completely elementary and ill out there。Okay。

Okay， let me prove this。嗯，么意思。By induction。Ons。Thank。Base case， degree one。Is P one。Yeah。

Which I'm not going to prove。对。Which is also elementary。

 but it's more more involved one has to do a little bit of work。😊，Okay。So n equals one。Is is blue by。

你 don吗。Otherwise。Let's consider this general case， general land。😊，And I'm looking at。B x1 up to Xn。

She。And let's look at XN， I want to induct， so let's look at XN。😊，And look at the highest power。

Of XN that appears in any of these monoomials。So let's say this is equal equal to xn to the K ofq of x1。

Up to xn minus1， so I've taken all terms of x n to the K and kind of pull them out。

Plus r of x1 or2 x1。This contains all terms where XN appears with the degree k minus1 or less and all the other terms。

 whatever。😊，Okay。😊，Good。So now I say what's the probability that p is equal to p of x？Is equal to0。

This is the probability that p equals0。Oh。Given。6一 equalゼ。

Hences the probability Q equals0 plus the probability p equals0 condition and  Q not equals0 and probability Q not equals0。

Yep。Right enough。And this is at most， since these are all probabilities， I can choose。

 I can pick and choose which of these terms to upper bound by one。😊，Okay。

So this is at most the probability。Of  Q equals0。Plus the probability p equals zero conditional and Q n equals6。

F了。Okay。Let's look at the probability that  Q equals0。😊。

How many variables there I the number of variables is。N minus1。So I can name duck。And。

What's the degree of this polynomial？那 no no。So d minus k。

So this is at most d minus a divided by the side of S。Plus。

So let's look at the probability that p equals zero condition on cuicles。😊，系。😊，So actually。😊。

What's the。You know Q is a polynomial in the variable x1 through x and minus1。

So what I could do is I could choose the random values I'm taking the probability space right where each x x1 x2 up to x n are being chosen independently。

😊，So I can choose the random values for Q， I can just condition on them。Okay。😊，P sorry， for the x1。

x and minus1。I condition on these values。What am I left with？XM。

So let's fix the values of x1 and x2 up to xn minus1， according to this condition。

And now I want to bound the probability that the remaining polynomial still goes to zero。

What's the remaining polynomial？This quantity is not0， that's what I condition。

So the remaining polynomial is the polynomial only in XN。With the term x n to the K。Plus。

 some garbage。WePa lower degree。So this is a degree K polynomial。In X。How many roots does it have。

 what's the probability will hit a root？你个的。对。No， I chose the highest degree guy， okay。

This is where I use the fact that I chose the highest degree。I mean。

 you could could you could do like two maybe maybe I could， but I don't forward into it it's。

 you know this is。This is just this simple。So that's the proof。It's remarkable for for。

Tarem is powerful。Actually， I mean， I haven't shown you the power。

 so there's no reason for you to believe that theorem is worth anything， right？😊。

But it's very clearly proof。是。How are you guys， James？

So I should show you why this theorem is worth anything。And why it's relevant to matching。对。

So let's come to low versus。Lo versus， by the way， the short ziplemma was proved in the years1979 thank you。

😊，Yeah， no， so so around then yeah， and Loas this paper also is in 1979 and he saw this and he saw this idea and said。

 okay， it's a useful idea okay。😊，So here' is the idea so the idea is。😊，嗯。Let's consider a graph。

 lets consider a bipartite graph。And I want to find perfect matching。

 so it better be the case that the number of wordts on the left and on the right are equal。😊。

Okay so this is a bipartgraph it satisfies that property and I want to check whether it has a perfect matching or not and it has a perfect matching。

 of course you know that's fine。😊，Given this graph， I'm going to write down。A matrix。

And this matrix is essentially the。😊，The adjacency matrix of the graph。

But wherever I was about to write a one， I'm going to write down a variable。

And I going to write down a distinct variable。So this has three distinct variables on that。

And I'll call this matrix the Edmunds matrix。Because this appears the first in a paper of Edmunds。

 but actually。去。You， actually there's a fact。Okay， this is a matrix which is full of indeterminants。

 full of variables。😊，Right。咩系。And I can talk about what its determinant is。😊。

It's determinant is just some formal expression， right？😊。

You know what the determinant of this matrix is this times， this minus this times。😊，So in this case。

 the determinant is x11， x22。Okay， the fact。The determinant。Of the Ed matrix offer graph。Yes。

Is not the zero polynommal。😡，If and only if G has a perfect matching。ok。😊，Rs。K know bogus。

 you know this is like a you know it is really right what is the determinant of a matrix。

 you know the la needs formula for a determinant of a matrix right。😊。

It's like over the determinant of a matrix with the sum overall overall permutations。

The belonging to Sn of negative one to the sign。Of this thing turns the product over I going from one to n of the EI sigma I。

Whatever， I mean I'm writing a fancy thing right I'm just writing what the formal thing for this this minus this times this is because this matrix that I wrote down is the bipartite adjacency matrix。

😊，These things correspond to the roles。And these things correspond to the Col。

So I should have clarified I'm cheating a little bit。X1，1。This entry corresponds to this edge。

This entry corresponds to this edge from one to two。Row one column two， this is row one。

 this is column two I could write this as row one row two column one column set the graph whether has yes。

O，不 but他好 can呢。然，这个主任啊。TheHBP稍。This is bipart graph there are two vertices there and two vertices here and I have edges between them。

😊，I don't want to confuse you guys。It's Friday， it's very easy to get confused。嗯。This is a graph。

 I want to check whether its perfect matching or not， I have one row for every vertex on the left。

 one column for every vertex on the right。😊，And I'm putting an entry out there corresponding to the set。

And this one corresponding to the engine， so and so forth。Okay。

 I am checking whether it has perfect matching or not and how did I do okay so Im going to say that the determinant of this matrix is a polynomia。

😊，Because there a bunch of variables and I'm just taking the determinant this determinant is non zero if and only if the graph is a perfect match。

嗯。😮，Proof。Well， come on。Each of these things。Is choosing。Some， some possible permutation， you know。

 what's a perfect matching in a bipartite graph a it's really a permutation。😊。

This and this are the two possible comment。And this is checking， this is giving you， you know。

You first look at this， that's the first permutation。

And this is indeed corresponding to some variables and if there is a zero out there。If I look at。出。

Go you guys， they don't have an edge so that term will die out。So if I look at each of these guys。

 they all， you know， this is equal to zero if any of these edges。😊，I， sigma， I。咩事。

So the only way in which I can get a non zero term is when all these variables are present according to sigma。

😊，And the sign is irrelevant in this case。😊，Because this product is unique。

According to the permutation。哎。So the determinant of this。Polynomial is non zero。

 if and only if the graphic perfect matching。So then you could just try and electro good， good。

But this determinant as such has n factorial terms。😊，I can't even write it down。

 I can't expand it out to see whether it's zero or not。And it could be zero for insidious reasons。😊。

You various things could cancel each other out。Not in bipartite graphs， but in general graphs。

But just let's start off by poetry。So there's determinant。

This object is a compact representation of a massive polynomial。But the good thing is。

That the degree。Oh this guy。Is at most。And thank you。

Yeah of that x like one two and x1 one is this just like one or zero。

 is there an edge or do we public the weight of an edge so x is variable？Right now x is available。

 I'm defining a polynomial。😊，And how am I defining a polynomial I'm writing down a matrix which is full of indeterminateants。

 full of variables。😊，But is it the Eddmins matrix like a matrix well it's matrix' it's just got variables in there。

😊，好ello。And then I can define the determinant of that object。

I said now a polym oh I see so it's it's zero if there's no edge and if there is an edge。

 you just make up a new variable， a new variable。Yeah， that's exactly what I think interesting。😊。

It's an advanced move， I mean， it's a very basic move， but you wouldn't have seen it。😊，ok。😊。

So here's the matrix， I wrote down as determinant。😊。

This determinant is non0 if and only if the graph is the perfect matching。

 so all I need to figure out is whether the determinant is non0。😊。

But I know that the degree that most10， so if I choose， let's say。S。To be。Of saless。

Let's say ends squared。To the field of size at least1 squared。真。Then。Take the E matrix。

And now actually substitute n for each of the variables。A random number between  one and n squared。

 whatever not between one and n squared from this set。So essence in subsequent some field。Really。

 if you do this in practice， you should really use finite finite fields and stuff like that。系。

So you choose s subs n squared， then I'm just saying the probability。😊，That。The the matrix。

 so what did I do I took this。😊，Mattrix and I've substituted in random entries from S。

And now I'll take the determinant of that object。But， that's。

A determinant of a matrix over a finite field that's that and that I can do that I can compute very quickly。

So the probability that this determinant。Ofい。Evaluated at some random point， R1 r2 up to Rn。

The vehicle equal to0 is at most n。Over that squared， which is one over that。咩。

So probably all I'm saying is， you know， this is a fancy way of doing the following。

 take your adjacency matrix， replace everyone by a random number independently。😊，From us。

Take the determinant of that。And the claim is if you get back a non zero value。

 then clearly you have a perfect matching。And if you get back to zero value。😊。

Then with high probability， you have a。Graph with no perfect matchings。Yeah。你 tell me you pass。

How fast can we compute the determinative matrix， you can use Gaussian emination to compute the determinative matrix and you can do this in cube tag。

But you can also do this in n to the omega time remember the omega exponent of matrix multiplication。

So there's a paper of bunch in hopcro referred to it out there。So you can easily， I mean。

 not whatever， either you can easily compute it in N cube time。😊，It requires gaing elimination。

 essentially。啊。That's a good question， you know， we've reduced it to determining computation。

 but we better do it fast。😊，So。嗯。不以。Great right。So in this kind。Basically9 to the omega time。

You can compute， you can figure out whether graph is the perfect matching or not。So far so good。

 everybody happy so far。是啊。Now， you might say， look bipartite graphs the really， in fact。

 I can run for F person。😊，Which you know takes essentially no time really I don't want to muck around with matrices in startup matlab and stuff like this。

😊，But so if you don't want to do that， then let's do something slightly more sophisticated。Same idea。

 by the way， this is the one idea today， actually the idea， yeah， this is the one idea。😊。

But if you have a polynomial。which has low degree if it's univate， then it has small few roots。

 you are happy if it multivariate。😊，Then it has a small， you know。

 you have a small probability of hitting a root。As long as you affected large enough。Yeah，因为钱。

Thank you。So how arbitrly close to zero would you like？😊，I don't know， more than。

Abit really close to so here's the good thing with randomizeds and I love this thing right？😊。

So what we did was we gave a test， let's actually you know make our life even harder。😊。

I'm going to choose S of size 2 n。😡，So the probability。That I make a mistake is at most one half。

Okay。😊，Good人。So I have a test。Which half， you know if you know， so so what's the words。

 let me summarize。This is。If the。Determinant of。二。Is equal to0。Then our test。Always says。

No perfect matching。Because if the determinant is zero， no matter what numbers you put in。

 you will always get back zero。😊，But if a determinant of E， which remember is the polynomial， right。

 this is a polynomial。😊，Is not zero。Then our test。Says。

Perfect matching with probability at least one half。Okay。

So I run this test once and I get this thing。I can basically repeat。Independly。Pters。If all T times。

Our test says。啊。No perfect matching。Yes。If all be。Sa。No perfect matching。男性。Rely明白了。呃。

No perfect matching exclamation point。Hence。四。Perfect matter， ex dimension finder。Whatever， right？

What's the probability of error now？Half to the tea。Yeah。嗯。So I can make it aarily close to ph。你出了一瞬。

こ就是生で。Oh， I'll make it independent this two is randomly。From。From the from the set repeatedly。Oh。

 actually。Now I see what was confusing you and in fact， I should have said this clearly。😊。

Suppose the。Suppose they enumerate over all possible elements of S to the N。😊，不。U。

What this is saying is。Like at most half the points。

Are going to be zero when the polynomial is not zero。

So if you enumerate over all points of S to then， half of them will be saying， oh。

 the polynomial is not0。😊，You will be able to design mindset。出嚟。Theres easier question。

 easier to answer than okay， justsica。But that's still important。You know。

 want you want to reduce the probability to 2 to the negative n just run it n times。

Due to the negative and smaller the number of particles in the universe， etc ce。Okay。Other questions。

 yeah like if you wanted to then here you have you can absolutely right so like it's generally so so it depends you know which is easier。

😊，You can optimize between the two you can think about which one is faster once you start getting your s to be large enough your appeal to be large enough it might not fit inside your word。

 you might be unhappy with that。😊，So your mileage may vary two different ways of improving things。个人。

Okay。😊，Myippart graph， very easy。No on bypart thinking。The same idea。And this is actually。

So let me just go over this thing very quickly， I'm not going to go over the entire proof but。😊。

I'll show you why the theorem is true， or I'll claim a theorem and I'll show to you why the theorem is true。

Here's a graph， non bipartite。Here is a matrix。And this matrix is called。The tut matrix。

 you remember tut we talked about him last time built tut he proved the。Tuck Burge formula。

So this was back in the 50s and he gave proof of the tubir formula using。😊，A matrix he defined。

It's a magical proof。😊，I still don't really understand that I know proofs of combinatorial proofs of the tu bch formula。

 but his proof is kind of mysterious anyways。😊，So you define a matrix。

What's the matrix so the matrix has。There are four bytc， so it's 4 by4。

And it's essentially the adjacency matrix， so it's there's an edge from one to two。😊。

They have an edge from one to four。There's an edge from two to1， two to three， two to four， etc。It's。

They are fresh， look at the upper half of the matrix。😊，All these variables are fresh variables。😊。

You know， x1，2， x 1，4， x2，3， x2，4， x 3，4。One corresponding to every age。

The ones downstairs are just the negations of the ones upstairs， so it's skematic。

A transpoes negative a。Yeah。And。Pem says。And this is due to third。嗯。And I'll call this matrix。P of G。

The determinant。F b of g。Is not the zero polynomial。If and only if G has a perfect matching。

Nice tail。And this is kind of what he showed in his 5th paper。And once you have this， you're done。

Same technology as before。Take the tu matrix， fills entries。With random numbers。But now， of course。

 every time you pick a random number， it appears twice。Computers is determinedant if it is zero。

You think probably the graph had no perfect matching。If it's non zero， you are lecture sure。

 the graph has the perfect magic。Because perhaps helps up。Yeah。The proof is not very difficult by。

By the way， does this graph have a perfect matching？😊，Sure， it does one， two， three， four。Okay。😊。

So let me show you。In this thing， one， two。So here the permutation corresponding to this perfect match。

I have chosen the variables corresponding to the edge of the perfect matching。😊，Okay。😊。

These terms can never appear in any other permutation they can't be canceled away。

So if there is a perfect matching， this polynomial has non zero determinant。😊，Once side done。问了。

By example。But really， that's the proof， okay。The other thing。啊。Suppose the determinant if not。

 Sarah。哎。😊，So what does the determinant not being zero correspond to？So let me， let me take。You know。

 all these kind of yeah， so so let me pick any any term in that light needs formula， right？😊。

Let me take any permutation， let's say I'll take this permutation。得得得得。You know。

 there are a bunch of permutations which have zeroes in them clearly they don't really。😊，Affect me。

Here is the permutation which doesn't obviously correspond。😊，To perfect matching。

 it's not like the the you know， the pairs that I picked。喂。😊。

What does this permutation correspond to？是。So this permutation， you know。

 any permutation is written as a sort of combination of cycles， right？😊。

So really I'm just taking those cycles in my graph。This is an even cycle。

Which can be broken into a collection of， a collection of matchings。

You know this matching and that matching it's and if it's a not cycle， then it'll cancel out。😊。

There will be another permutation which will cancel out。You know， you go take the cycle this side。

 take the cycle that side。😊，The signs will flip because it's gesymmetric。Yeah。That's proof。

 you just sit in formula。That's proof。And therefore， this immediately gives。Therefore。

TheCral re phase that exist。Algorithm。嗯。啊。Order n the omega time。都。Detect。Perfect matches。

With high probability。We个。😊，你可以。We all a break method。I you， in some sense。

 the polynomial method was the the thing to take away the fact that you took an object which has nothing whatsoever to do with。

😊，Marices linear algebra， polynomials， you pulled out a polynomial。

Whose properties are capturing combinatorial properties of this object？

Is the powerful tool and every so often you'll be like， yeah， okay， I can write this polynomial down。

😊，The roots tell me something。Or in this case， Im just just the degree。The determinants。

Of this matrix is this polynomial whose non zero value tells me。The powerful lady。Questions。

But he said to the state of the art for finding it。

Perfect matching for gentle perhaps suppose what nanny would in， but this does hamster。Yes。

 depending yeah， so previously I said M root and this does into the omega。😊，So if M is dense。

Then this is 2。5。And this would be 2。3 something。But。The reason why I was hemming was。

All I've told you is this graph has a perfect magic。😊，How you want to find the perfect man？

This is random that result was deterministic but you know， come on what's randomness between friends？

😊，Yeah， no it's a yeah， I mean this is different right and that it doesn't actually find the perfect magic right since there is exactly so so let's ask a quick。

😊，So by the way， from now on， I'll imagine that you've either chosen your field large enough。

Or we are set S large enough or you repeated it many times。So that。

I can detect with high probability with probability 1 minus1 over polynomial。

That it's got a perfect matching or not。The errors are very small probability。

 let's say for the moment， just imagine that the errors are not there。😊。

So the question I have is if you can detect whether a graph has a perfect matching。

 can you find a perfect matching？😊，TAs are not allowed to respond to answers。Good questions go。

So if if you can if I can， if I give you a box that can find a no that can decide whether there're the perfect matching or not in the graph。

😊，You feed it a graph， it tells you yes or no。Can you find a perfect answer？下一个哦，OK那能下一个。😊。

It depends how it tells you basically it's a box， you feed it a graph。And out comes the answer。

 yes or no。Yeah。It's made in a brief。Doesn't waste。Effent。So take a graph。Suppose it says no。

 then there' is no perfect match， suppose it says yes， to remove your favorite edge1。😊。

If it still says yes， this edge was not relevant， you know。

 there is a perfect matching that doesn't include this you can throw this one perhaps。😊。

On the other hand， it says yes。Or if it says no， it used to say yes on this graph。

 but after I removed my favorite tag， it says no。😊，Then all perfect matchings must contain that edge。

😊，So you can remove those two ver seeds from the graph。

Because those two must be using that edge in any perfect match。That's it。So you know。

 it says your decision， whatever。That's you know， G minus E。You ask g minus E if it says no。

Then it says that E is in the perfect matching。And if it said， yes。Then just continue on g minus。

Okay，How much time does it take you about to say like does that multiply or runtime by a factor of M which is like good bad so so this takes M times n to the omega time。

😊，Okay， can we do faster？And even if you guys have lost me back there。

 you should you know feel free to think about this thing。

 I give you a box that finds that tells me whether it's a perfect matching or not。😊。

How will I find the perfect shell？It reviewed a thing where we remove the ver after we say that the back doesnt that mean every time we on it。

 we reduce the number of words so it's adding times。No。

 that's so imagine that basically every time I asked the question。😊，It said， yeah。

 there is still a perfect matching without this edge， I was just fooling you， I was just， you know。

 if you so you might have a lot of edges that you remove before it finally says no。😊，You know。

 until then it might just keep saying yeah it's there're the perfect matching without that end you might just get un very nice so here's the other idea you pick your favorite verortex v。

😊，And it has a bunch of edges。You remove the first half of the edges。And you say。

 does it still have a perfect matching？😊，If it does， you've removed half the edges。If not。

We have removed the other half of the edge。嗯。L again。个人。Can we do better？

So now it gets a little hairy as far as I know。I know at least one way of making it n times n the omega in fact。

 the lecture notes contain that proof。😊，But inna， it's a little more detail oriented than I want to do on a Friday afternoon。

嗯。喂。Then there were these two PhD students。 In fact， I love highlighting these。

 these proofs which were actually done by PhD students。 So oh， this was a paper of。😊，嗯。

Michael Robbin。And Vijawajirani。So。呃。Michael Rabin was actually the guy who is often credited with the first use of randomization in algorithms。

 the Miller rabin test for primity is very commonly used to check whether the number is prime or not。

😊，And he's the he's the ra of that Virani he's done a bunch of very fundamental work on matchings so they had this result and then these two grad students from Warov figured out how to。

😊，Martin Mucha and Piat Piore Sowski。For their PhD work。

 they figured out how to get an enter the omega runtime algorithm。And。And this is the you know。

 this is essentially the best known because we have to compute at least one determinant。😊。

And all of these are randomized algorithms。But to answer your implicit question。

 can you use the same idea in a deterministic framework？😊，And well。

 you know this is a very specific question so you could derandomize this without actually solving the P versus BPQP problem BPP by the way。

 those of you who haven't seen this is bounded error probabilistic polynomial time。

 fancy name for randomized algorithms which are in polynomial time。😊。

I mean you should take a complexity class sometime and they'll tell you about the distinctions between these questions I mean these are like the fundamental questions like what can be computed is random as important？

😊，How fast can we compute these things， what can we do in log space anyway？

I will get carried so you can ask the question， can you do the same thing。

 so all these are randomized。😊，Deterministic people figured out how to use this approach deterministically。

In polynomial time， but it takes a little worse than endonic。

So I don't know how to get a deterministic into the omega runtime algorithm。下。But then， you。

 I am perfectly happy with trying the my job。是。But even if you go the deteristic， you get this。

 which it' already randomized。Yeah， so if I deterministic I won't even need to repeat independently when oh so so so all these reductions were kind of deterministic but the sort of underlying black box my perfect matching detection black box is randomized so derandomizing that is the real question。

😊，个人。Okay， let's take a two minute break。And then I'll tell you guys a little more about that。

So you know here I have to make a decision whether I'm going to tell you about one thing or the other。

 so instead of telling you about parallel algorithms for matching。😊。

It's let me instead tell you about an open problem。啊。Red blue perfect matching。

 So we talked a bunch about randomization， deterministic algorithms。嗯。

So matchings we know how to find deterministically。General graphs。嗯。

Bypartitegraph everything we can do deterministally。So this was nice。

 they maybe gave faster algorithms in some cases， but we。😊，At least， you know， if we want it。

 we really have a deterministic algorithm。So now I'll give you a problem for which we have a randomized algorithm。

 but we don't have a deterministic quality time algorithm。😊。

And since know I'm touting all these results that people have proved for their PhD。

 hopefully some of you can prove this for your PhD。😊，So it's a nice question。

So this question is called red blue perfectf matching。😊，I give you a graph。啊。

Which I've already seen in that is。And the edges are partitioned into two sets。Rビ。F。

So I give you red and blue。And I want to find。呃。Does there exist？A perfect matching。为。这。哎， much。

Exactly care。Yeah。For this， there exists a randomized polytime algorithm of them I'm going to sketch it for you。

It doesn't exist at determinist。That yet。We don't know one yet。处备佢。啊。Is G bipartid？Yeah。

 maybe ge bipartid， do I care， I don't think I can。Yeah， let's say Jesus by birthday。Yeah。

Yeah so this one is it' it's more assoteric in the sense that this one okay there's some motivation behind this but essentially I think people are like can we solve this problem we don't know how to solve this problem so it's become a challenge problem just because we don't know how to solve it。

😊，Because it's there in some sense。啊。There are some applications to some of these exact optimization problems。

 so for instance， if you can find MSDs or does there exist a spanning tree with weight exactly 53。

So this is a subroutine in computing the parreto curves， people want to compute parreto curves。😊。

They ask questions like this， but for this one， I don't know for sure。嗯。So more than any other idea。

 I just want to illustrate a couple of simple polynomial tricks。😊，That you might have forgotten。

 that might be useful to remember while doing a。Okay。

So graph the perfect matching exactly K right edges can you solve that。😊。

Its like if K is like bigger than you can believe you can do like September that's good mine is。But。

 I don't know。But we know one side had well no。If you're using paid reds then you're using and I mean in fact let's imagine it's a bipartite graph and there are n vertices on this side I'm abusing notation out here let's say there are n vertices on this side。

😊，So I have I'll have k right edges and n minus k blue inches。😊，诶。😊，Okay。Um。

Suppose and this is you know one of the tricks one of the goals is to teach or remind you of various problem solving techniques right yeah second variable like。

😊，Okay now very nice， very nice。SoSo let's look at a special case。😊，啊。They exist exactly。1。

I'll call this。Such a perfect matching， a K。Perfect matching。

Suppose there exists exactly one K there。Perfific matching。Okay， can you find it now？

And what are we going to do？Is let's define matrix a。Which is。

So these verticCs are numbered one to up to n， one to up to n。

All the edges remember are going between sides， right？So AIj is zero。If。I comma J is not an image。

 of course。It's one。If I call my jail。Even edge， and it's in the blue center。And it's why？Yes。

I comm1 J is in the red sector。好嘞。Why， variable why？😡，Why I no， why， in this case， why？Okay。😊。

So now let's look at。The determinant。哦是对。Remember， as before， we were saying， look。

 what is the terms in the determinant of a， they all correspond to permutations。😊。

They all correspond to。嗯。The first term might be something like this。

 the second term might be this permutation。😊，And so on and so forth。Look at any permutation。

If all the edges are in the graph。Only then will you get a non zero value。对。嗯。

And what term will you get？You'll get y to the number of red edges。So this is going to be。

Some overall possible for mutations。西igma。off。The indicator of whether sigma。Belongs。

To the graph or not。So it's going to become zero if this is not a matching。So really I'm。

I should just ignore all this and say this determinant will become summation over matchings of the graphs。

Perfect matching。OfG。Of negative one to the something。Times y to the number of red edges。嗯。The match。

Okay。😊，It's some determinant。Same problem as before， this determinant is some beast。

But what do you know about this determinant？It's a uniate polyno。Maximum degree。Actually。

 maximum degree could be n doesn't matter。边得落食啲。怎么。Me， you know， so actually。

 maybe I shouldn't say exactly once that exists。At most one。

Either they exist zero K right perfect matchings or they exist one K right perfect matching I want to distinguish between these two cases。

😊，No perfect， no K red perfect matchings or one K red perfect matching。诶。

This polynomial has something， something， right？So this has y to the K。Times。

The indicator of there exists a K red。Perfect matching。Plus some garbage。

Can this term be canceled out by this？No， because we said that at most one k at perfect matching。

There's one0 or 1 K rate perfect matchings， which will decide whether this term exists or not。

And there's some other garbage。It's a polynomial of degree。嗯。

What do you know what polynomials of degree D？How would you figure out？A polynomial of degree。

This is some polynomial of degree， let me call this peak。😊。

I want to figure out what this polynomial is， I want to nail this polynom completely。

 I'm going to figure it out。Can you suggest a way in which I would figure out how what this polynomia is？

Efficiently。Inpolation。哦因。So my claim is suppose I know the value of p of y。

 suppose I know the value of p of0， p of 1。B of N plus one。啊，不要烦，在吃哪。

These are n plus one different points where I know the value of this polynom。Then from this。

 I can reconstruct the polynomial。There's no La grande interpolation if you rather forgot。

And you know， in the last five minutes， we can do that range interpolation as well。

If you guys haven't seen this， it's a beautiful idea， but anyways。😊，First。

 let me just give you the punch layer。嗯。Can you compute p of0 fast？😡，对好。

I can substitute zero in there。It's no， no， no， I'm not good doing that I have this matrix。

I can substitute a wear out here。Now， this matrix now will have only ones in zeros。

I can compute this determinant。That's the value of P of0。I can substitute 1 there。

 that's the value of p of 1。I can compute， you know， substitute 7 that that's a value of P of7。

So each of these is requiring one determinant computation on numbers。No polynomials involved。

To compute each of these values。Once you know the value of a polynomial at degree plus one points。

I claim you can reconstruct the polyno。So you can write out this whole list。And you check。

 is there a term corresponding to y to the K？If there is。You have a K perfect patch？

Kay right perfect matching if there isn't， you don't have K right perfect matching。诶。😊。

Now this is the new word。all the terms， but I don't need all the terms。

 all I need is just figuring out whether this term y to the k has a zero in front of it or a one in front of it。

😊，You still seem worried it。这。TA are not allowed to answer questions。

 but theyre allowed to ask questions。😊，😀对呵呵。😊，Here is some of B plus one product terms in the Lagrin polish。

Sure。peHow do we accept the？I mean， there's a derivative you can accept that。😊。

They're many different ways， so I'm imagining that there is a black box that I have where I can feed in and plus one points and it'll give me back to poly。

😊，In let's say， a sort of compact form。And this I can implement。So far， so good。

I didn't use any randomization at all， but。So another another advantage of using polynomials。

 you can use ideas like interpolation。😊，Which you had no reason to believe that interpolation would be useful in finding matchings out here with it comes up。

😊，是。So maybe I'll just mention very quickly。How do you get rid of this assumption that there's at most one right perfect matching？

是。So in order to get rid of this assumption， what you'll do is you'll do exactly the same tricks as before。

😊，You're going to throw in these auxiliary variables， you'll do a similar argument about there being。

A term corresponding to y to the K。According to you know these sort of y to the k times some product of x's。

 those will correspond to the K at perfect matchings and you'll do a similar randomization right。😊。

Let me not go into that。你讲佢咯。The coefficient because of the negative one。

 they might cancel out so you need to be careful that's the whole idea that thats that's where we run into truck。

😊，So maybe in the last one minute that I have， let me not do anything else。

 but let me tell you about La Grand interpolation if you've forgotten this is a very useful thing。😊。

So let me say I have a polynomial。Be your facts。Is something x squared？

Pluss something X plus something。嗯。I know。The value of P。A these points。I know it's value at p of0。

I know its value at p of3， I know it's value at p of 7， these numbers have been chosen without hurt。

And this number is nine， this number is actually p of1， let's say。

 and this is a negative5 and this is two。Okay。😊，And I want to figure it out。嗯。Wk。Bees。行。

Let me actually do the following thing。I don't know how to do all this just。

So let me try to figure out a polynomial where P of1 is 1。P of three is zero and p of seven is zero。

Can you give me such a problem？And it should be a quadratic because， you know。

Qudraatic three points should determine the quadratic。Okay，X minus three， first。

 forget about this guy。It's zero there at three and seven。不。

But now I need to make sure that it has value one out there。W minus0 minus。

This is a polynomial that has 10，0 out here， right？Similarly。

 you can write down a polynomial which has0，10。And0，0 one。So this is the polynomial。

 let me call this to。进融。You why。小猪。But Q1， Q3。Thank you，7。Right？I've figured out three polynomials。

 first polynomial has these values at these three points。

 this value has 010 and this polynomial has 001。😊，Com on past， you're done。です。This and this。

 the former basis of our space。So can you give me a polynomial which has values  nine。

 negative5 and 2？It's9 times Q1 plus negative5 times Q3。Plus。Do dance就赛。

That's the polynomial that has those values at those three numbers。对。Likerian interpolation。

And if you haven't thought about the Chinese remaindering theorems for a long time。Same idea。

It's the same principle。I urge you to go back and try to prove the Chinese remaininging the on。Yeah。

 society。Anyways， I should stop here， you guys should have a good weekend see you us。

