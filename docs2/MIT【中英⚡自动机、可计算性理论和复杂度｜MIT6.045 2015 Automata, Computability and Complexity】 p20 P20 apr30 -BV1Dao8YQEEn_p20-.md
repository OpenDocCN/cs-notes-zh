# MIT【中英⚡自动机、可计算性理论和复杂度｜MIT6.045 2015 Automata, Computability and Complexity】 p20 P20 apr30 -BV1Dao8YQEEn_p20-

嗯。Okay， so。Welcome to。诶。The home stretch， so PSet4， I finally do have graded for you。

 you can pick it up after class， let's see， this coming Tuesday， I'll be away at a conference。

 Robin will be lecturing，So last time we talked about the basic theory of modern private key cryptography。

 which is fundamentally based around the concept of a one- way function。

 a function that is easy to compute but intractable to invert， to get pre imagesages of。Now。

 you know， in order for one way functions to exist。

 certainly we need that p is not equal to NPp okay， but even if p is not equal to NPp。

 the belief that one way functions exist is a further conjecture。

 it' a stronger conjecture beyond that。And you'll actually on piece at six， you see exactly how so。

 okay， but once you assume that you have something that's a one way function， you know。

 and the truth is it's not that you know wild an assumption right because like any kind of。

kindind of complicated looking transformation of the input you know that you could make up。

 you know you can conjecture that it will be hard to invert and you know you might very well be right so you don't sort you don't seem to need any very。

 very special mathematical structure in your function in order for it to be plausibly one way but what we do know for sure is that once you have one-way functions then you're really cooking you can construct from that you many。

 many of the basic primitives of the basic things you would want in private key cryptography so you can create a pseudoranom generators for example。

 and once you have a pseudoranom generator then you can have a secure private key cryptoytem which unlike the one-time pad you only requires very small keys。

嗯。Okay， so but you know in the modern world as we discussed last week。

 what we really want is cryptography that doesn't require you a shared secret key because know it's just impractical to have every two people on the internet who want to share a secret message you meet each other in advance to agree on a key okay so that led to this you know at the time a radical idea of public key cryptography which was developed in the 1970s。

 you know first secretly at the GCHQ and then in the open by Diffy and Helman and by RSA okay so you know I gave you a little analogy last week about how this public key cryptography might be possible if the analogy didn't help you then just forget about it okay because today。

Iell you how it works for real。嗯。And then if we have time， we'll see a really。

 really cool application of the RSA crypto system to doing something you might have thought was impossible。

So let's start though with Diiffy Heman， okay， because that was historically the first one。Okay。Okay。

 so you know our basic problem is the usual one here， Alice wants to send a secret message to Bob。

 but Eve is listening in on the channel okay but now you know one thing that we already know is that you know as long as we can get Alice and Bob to agree on a shared secret key。

 you know as long as we can get them to share any kind of random secret that Eve does not also know you know then we're done right because at that point we could just use that secret as the key for a one-time pad for example。

 you know or if it's not long enough we could stretch it out using a pseudoranom generator so our goal。

 the goal of the diiffy Heman protocol is just going to be to get Alice and Bob to know something in common you know something random okay？

Eve doesn't also know okay， right because we agree that once we have that we can then they can do cryptography。

 then Alice can send a message of her choice to Bob you without Eve knowing what it was。All right。

 but now you know at first glance， you know， this seems like a fundamental impossibility。

 okay because Alice and Bob don't start out agreeing on any you know knowing any shared secret。

 right， there's nothing that they both know that Eve doesn't also know and furthermore。

 everything Alice and Bob say to each other is going to be listened in on by Eve。Okay。

 so how could they possibly come to know something together that Eve doesn't also know right it's like。

 you know imagine that they're playing this you know game of monkey in the middle right that they're you know throwing like a ball and you know Eve is going to try to jump up and catch anything that they said okay。

 how can they how can they possibly elude Eve all right。

 so the solution to this is going to involve you know。

 well you know still you know a tiny bit of number theory okay so？😊，So the idea is。

We're going to pick some huge random prime number P okay， you know， either one can pick it， you know。

 let's say Alice Alice will pick it， you know it could even be given to them by a third party that's okay also you know and Eve can know P also okay that's okay right you know so Alice can just send P in the clear over to Bob okay so everyone knows P。

All right。And now the shared so every prime number is associated with a multiplicative group there's the group of all of the integers。

 mod p right you guys know this like so basically there's all the integers from0 up to p minus1 and I can multiply any two of the or sorry that's not what I meant to say I meant all the integers from1 up to p minus1 from1 to p minus1 these are a group under multiplication mod p right I can multiply any two of them and you know take the result mod p and that gives me another number mod p okay and you know and these you know satisfy all the rules to be a group right。

So you know we call that like a ZP multiply this is the multipl of group mod P for example。

 if P were five， then we just have the group you know1， two，3。

4 okay under multiplication so you know you multiply two and three。

 you get one you multiply two and four you get three。

 multiply three and four you get two right everything is modD5 okay so so we look at the multiplicative group mod P now Alice and Bob are going to try to agree on an element in this multiplic of group that Evet will not also know okay。

So how are they going to do that？All right， well， the first thing is。They're just going to pick。

 you know， Alice can now pick an element of the multiplative group uniform， you know。

 just completely at random okay she'll pick this at random and she's also going to send this out in the clear all right。

 this doesn't look very promising so far okay but you know she can send that out so now you know Bob knows G Eve also knows G okay。

Right， okay， then you know， she's going to pick。She's going to pick a random exponent A okay， A。

 she's going to keep secret for once， okay she's not going to announce that。

But now she's going to do you know， a computation， okay， which is that。

She's going to compute G to the A mod P okay now you know now now already here there's a question that we have to answer right which is a could in general so to think of p as an integer that's like n bits long right so you know p is could be like as large as2 to the n you G could also be about as large as 2 to the n and A could be about as large as 2 to the n okay so ats now needs to raise G to an exponentially large power okay and now the question is how can Alices do that in polynomial time？

Does anyone know how to do it？Repeated squaring， yes， there's a trickrek to it。

 so you know like the naive way to raise G to the A power would just be a。

Multiply G times g times g times g times g and so forth， you know a times okay。

 but if a is exponentially large， then that's not going to be efficient。

So what you can do instead is that know you first represent a as a sum of powers of two， you know。

 any positive integer can be written in that way， for example。I don't know if a is 27， right。

 what is 27 as a sum of powers of  two anyway？Well。Two to the four plus。Two to the three。

 now we're up to 24 plus yep。Yep， two to the one， I'll call it two to the one and plus two to the zero Okay。

 there we go， it's just equivalent to writing it in binary notation Okay。

 but now we can think of that。So now， know if we have G to the A。Right， you know， it is G to the 27。

 we can just think of that as G。G to the two to the four times g to the two to the three times g to the two to the1 times g to the two to the zero All right。

 how does that help us Well you know if you're raising a number to a power which is itself a power of two。

 then all you have to do is just keep squaring the number。

 the appropriate number of times until you're up to what you want Okay， so this is G squared squared。

Squared， squared times G squared， squared。😔，Squared times G squared times G。Okay。

 and so now you know you know we've computed G to the 27th power using far。

 far fewer than 27 multiplications we use how many1，2，3，4，5，6，78，9。

 and then we got to multiply all these things together so 10，11。

12 I guess 12 multiplications at any rate fewer than 27 okay but you know the asymptotic savings is enormous right if a was like something you on the order of you if a was like 1 thousand24 bit number right then this would be on the order of know a few thousand multiplications rather than you two to the thousandth power multiplications okay so and now you know a key point is that all of these multiplications or being done module if we weren't doing it module P than very quickly as we discussed before with the non-zero circuit problem。

😊，If we kept squaring numbers， that would just very quickly grow to an enormous size where we would need exponentially many bits even to just write them down。

But。Because everything we're doing is mod P， you know， we just keep multiplying， you know。

 reducing my P and the numbers never exceed n bits long okay， so we can do all of this efficiently。

 meaning in time polynomial and N。All right。So with that said， Alice computes G to the A mod P。

 you know， in polynomial time， and now what she's going to do， she's going to again。

 you know just send this over to Bob， right？So now Bob also knows G to the Amin P。Okay， and Eve。

 of course， who is eagerly listening in， also knows G to the A might P。Okay， but now。😊。

Our hope is that at least there's something now that Alice knows that Bob and Eve might not know。

 what is that thing？A， yes， now notice that in principle。

 Bob and Eve now do know everything they need to know to determine A right because you know like Eve。

 you know she knows G， she knows P， she knows G to the A mod P she could so finding A would now just be a matter of solving an equation right she would just have to find the A such that you know G to the A mod P you know equals the thing that she that she just saw okay you know and she could in principle work backwards to do that but you know this would require to calculating what's called a discrete logarithm because you it's precisely that it's a logarithm but mod P yes。

That's true， that's correct， there might be multiple A's。

 so let's assume for simplicity that the A that Alice has picked is。

From one up to p minus1 all right， that will make the solution unique you know， that's not important。

 but you if that weren't true if a could be larger than that and the truth is the only thing that we would ever care about a anyway would be is what is a mod p minus1。

That's the only property of a that would ever matter in any case， but so for simplicity。

 let's just assume that a is from 1 up to p minus1。😊。

So then then if we call the thing that Eve has seen， H， let's say then。

Then Eve would now merely need to solve the equation， G to the A is congruent to H mod P。

 solve this for a， given G and H and P okay， this is a known， this is a famous computational problem。

 almost as famous as factoring， okay， this is called the discrete logarithm problem。Because you know。

 you can see that it's like， it's basically， you know， you could if you rewrote this。

 like you're trying to solve to compute。The log of H to the base G， but do it mod P？

So this is the discrete algorithm problem to solve this equation for a。

Okay now we do not know to this day a polynomial time algorithm for discrete algorithm。

 at least not running on a classical computer okay we do know a quantum algorithm for it okay now in practice the discrete log problem seems to be very very closely linked to factoring okay in like every time there's been an advance in factoring algorithms it's led to like an analogous advance in discrete log algorithms and vice versa and when when Peter Sho discovered as quantum algorithm for factoring which you know we'll talk about a few lectures you know at the same time he also found a fast quantum algorithm for discrete algorithm okay so that also exists okay so these two problems seems to you know rise and fall together okay and yet you know formerly we do not to this day no any reduction between。

Okay， there's no formal proof that if discrete log is solvable in polynomial time。

 then so is factoring or vice versa， it's just an empirical observation at this point。Okay， but。

Anyway， okay， so now you know the hope is that you know for Eve to learn A you know is going to require her to solve the discrete logarithm problem right you know in which we think is a hard problem okay or we take her you know exponential time all right。

 so that's good but you know that still doesn't get us what we want because there's still you know now fine Alices know something that you know Eve doesn't know but Bob doesn't know it either you know what good is that all right。

 well but there's a you know there's a further trick all right so now Bob is going to pick。

Another random number B， let's say from 1 up to p minus1 at random。Okay and。And now Bob。

Is going to compute G to the B mod P。Okay， and he's going to send that over to Alice， okay？

So now Alice knows G to the B might P， Eve also knows it。Okay，So Eve in fact knows， you know P。

 she knows G， she knows G to the A， she knows G to the B all right， so you know。

 this should be making you nervous， right， Eve knows quite a lot at this point。

 okay and I haven't written anything that Alice and Bob both know， but that Eve doesn't know。Okay。

All right， but I claim that at this point， Alice and Bob can both compute something that Eve plausibly will not be able to figure out。

 what is that can anyone see what that thing is？Well， you know， we're going to use， you know。

 Alice does know something that no one else knows， she knows A。

 and Bob knows something that no one else knows， he knows B， and， how can we leverage that？Yeah。

 G to the AB， okay， so now at this point， what Alice is going to do is she's going to take G to the B。

 which Bob sent to her and raise it to the A power。Okay， and what's that， that's just G to the AB。

Myd pig。As always， and what Bob going to do， he's going to take G to the A， which Alice sent to him。

And he's going to raise that to the B power， okay， so that again gives him G to the AB might P。

All right， so now Alice and Bob both know G to the AB， mod P。

Okay but it is you know but Eve you know doesn't know A or B right， she just knows P， she knows G。

 she knows G to the A， she knows G to the B and you know you can try combining these however you want but I predict that you're not going to get G to the AB if you do get it please tell me okay you know you know I mean it will probably have to be classified as a national security secret okay but but do tell me right if you can figure out how to get G to the AB efficiently from these numbers all right certainly you can get G to the A plus B and just multiply these two okay but that's different right so。

😊，Now it's not obvious that Eve couldn't do it，诶。You know。

 so we simply you know at this point we simply just assume that she can't do it。

 this is called the Diffyhelman assumption okay you know in fact like it's not even obvious that even if we assume that discrete logarithm itself is a hard problem you know maybe there could be some other way to solve this problem maybe if you know you know G and G to the A and G to the B and all you wanted was to get G to the AB。

 maybe there could be some shortcut to getting that no one has proved that there isn't one okay that's a further assumption you have to make you know。

 namely the diiffyhelman assumption okay but but if if you make it that it's computationally intractable for Eve to learn G to the AB given the information that she has now then you know Alice and Bob now have a shared secret which is not shared by Eve。

 namely G to the AB might P okay that's the diiffyhelman system。You know， know。

 whether you know it or not， you've used it many times， you know， when you've， you know， you know。

 done stuff over the internet， you know， like you know， anything and you know， involving HTTPS。

 you know， okay？So。um。All right， so how about RSA？So RSA is a different way to use cryptography to achieve this seemingly impossible right know and it's really it's very comparable。

 to diiffy Heman like you can use one， you can use the other。

 know the comparative strengths and weaknesses of them are like a subject for for cryptographers who will sort of drill down to a lower level of detail than we tend to cover in this course。

 they're both you at some level very very similar systems okay。Okay。

 but RSA is the one that's going to be based around the famous factoring problem rather than around the log。

 and also RSA is going to be a little bit more direct in that instead of you know。

 Alice and Bob agreeing on a shared secret key， we're just going to directly solve the problem of how can。

How can Alice send a message。To Bob， you know which Bob can read， but which Eve cannot okay。

 and so so now we're going to you know introduce the concept of a public key and a private key。Okay。

 so now you know although Bob is the recipient of the message。

 you know the first step in RSA is done by Bob okay you so for example you know if you wanted to send your credit card number to Amazon right then the first step in this process is going to be done not by you but by Amazon okay Amazon is going to have to generate a public key and a private key for you to you know for you to then use in you sending them a message securely okay so so what are they you know what is Bob or Amazon going to do okay the first thing they're going to do is pick two a huge random prime numbers which we'll call P and Q you and once again you know the same thing is in diiffy Heman here we use the fact that first of all you know there are you know you know you know that prime numbers are quite common even when you go up the huge numbers。

If you pick like a random thousand digit number it has a one in a few thousand chance of being a prime。

 which is pretty good you just have to pick try out a few thousand of them before you're going to hit a prime that's because of the prime number theorem okay and furthermore that we know how in polynomial time to test whether a number is prime or composite we're also crucially using that fact。

Okay， so Bob can do this， he can pick two huge random prime numbers， okay。

 he's going to want for reasons that we're going to see。

 he's going to want an additional property of them。

 which is he's going to want p minus1 andq minus1 to not be divisible by3。Okay， so you know。

 but but you know there are lots of primes that are like that， you know。

 in fact you know about half of them are like that okay so you know， three would work。

 five would work， seven would not work you know， 11 would work。

 13 would not work okay so you know about half of prime satisfied this property so this is you know and one can prove that and that's not and so this is not hard to get either all right。

 now these P and Q， this is going to be Bob's private key okay he's going to keep this a closely guarded secret you know under his pillow。

 whatever he's not going to tell anyone okay but then he's also going to multiply them。

Okay to get a composite number n n is his public key okay。

 his public key he will share with anyone who asks。

 okay you know and he may send emails that have something at the end that says begin PGP you know sign you know you know a key or whatever okay so you know he just you know he can put the he can put an in the signature of his email okay。

 that's fine so he sends。You know， he sends and Alice， then of course， Eve also learneds Anne， okay。

 and at this point we already observe that you know。

 to know everything Bob knows and therefore break the system is merely at worst a matter of factoring n okay if you can factor n into P times Q。

 then at that point you know Bob's private key and the system is completely broken。Okay， so。

 you know at the very least， we're going to be relying on the assumption here that factoring is a hard problem。

😊，Okay。Fine， you know， nothing ventured， nothing gained okay now the question is Alice has some plain text message X and now how does she communicate it securely to Bob okay。

 so what she's going to need to do is you know encrypt X using N。

 but in such a way that it can only be efficiently decrypted by someone who knows the factorization of N okay this is now the problem that RSA have to solve。

😊，Okay，'s。😊，Okay， so now you know we just need a tiny bit more number theory， okay。

 so I'm going to assume for simplicity that x is an element of the multiplicative group mod N okay let me now define this。

Okay， so ZN times is the group of all the integers from one up to n minus1 that are relatively prime to n okay under the multiplication operation okay and you can check that that set of integers forms a group it is closed under multiplication moded。

 okay if we added something that was not relatively prime to n， then it would no longer be a group。

 okay。And that's important Okay， so let's do an example， let's say that p is 3，q is 5， okay。

 so n is 15。Okay， so what does the multiplicative group mod 15 consist of？

Someone want to list the numbers for me？Well， it's got one。Does it have two？Yeah， does it have three？

Nope， does it have four， yeah， does it have five， does it have six， no， does it have seven？

Does it have eight。Does it have nine？Nope， does it have 10， does it have 11？Okay， does it have 12？

Does it have 30。Does it have 14？Yes， all right good all right。

 so now you know you can check that these numbers do give rise to a group by multiplication modd 15 okay。

 for example four times 11 that's 44 modd 15 that is 14 you know we can we can have fun with this all day if you want okay seven times 11 that's you know 77 modd 15 is what is2 there you go all right so these guys are a group okay。

😊，呃。What's the okay， the you know， as you can see， this this particular know group is a group of order8。

 okay， what you know in general， you for an arbitrary P and Q。

 what would be the order of the multiplicative group， mod PQ？So we saw that if P is a prime。

 then the order of the number of elements in the multiplative group might p is p minus1。

 but now I'm talking about a composite number， p times Q， where P and Q or prime。

 okay I'm asking what's the order of the multiplicative group， mod P Q。Well。

 you know we've got it basically it's， you， it's you know， P times cube。

 then you've got to remove all the stuff that's relatively primeed to either P or to Q。

 and how many things does that leave you with？T。So。

So the answer you know which you can check is p minus1 timesq minus1 okay and you can see this because its you know it's p times q but then youve got to subtract out all the stuff that's a multiple of Q and there are p of those and you got to subtract out all the stuff that's a multiple of p and there's q of those right but then you know there's one guy namely n that we've subtracted out twice and it should only have been subtracted out once so we add one and this is equal to that okay so。

So this p minus1 times q minus1 is the order of the multiplicative group mod p。

 this is the number of things that are in play if we're talking about multiplication mod n。Okay。

And the reason why relatively prime to n is important you know， is easy to see。

 like let's say that we took three and five， for example， right， what's three times five mod 15？

Zero okay， but you know， but this this should never happen right it should never happen if we're dealing with a group that you know we multiply two things that are you know both non zero。

 we got something zero okay that's just you know。So， if we want group behavior。

 then we got to look at the things that are relatively primed dead。So having said all of this， okay。

 now what's going to be convenient to assume is that whatever plain text message Alice wants to send to Bob。

 it is some element of the multiplicative group mod N okay you know of course maybe maybe you the message is longer than that。

 if it's longer what can we do about that？Yeah， just split it up， you know。

 just split it up into a bunch of pieces and you know encrypt each one separately right so you know we can assume that the without loss of generality that the message is short enough that you know it's at most log of end bits or whatever so that we can encode it as an element of this multiplicative group okay in a suitable way。

We're actually for you know one thing that you have to be， you know。

 this is just just like an example of how careful you have to be when doing cryptography。

 one thing you want to be careful about is that before encrypting your message。

 you know you better pat it out with some random garbage， okay why is that important？Anyone？

Why should you not just encrypt your message without first patting it out with something else？sure的。

Well yeah， well you want to make sure that Eve cannot tell when you're sending the same message again。

 okay if you were sending you know you know the same message over and over。

 you and if every time you sent that message it encrypted to the same thing then even if Eve couldn't read the plain text she would know that you were sending the same thing okay and that would give her some information that would give her some leverage you and she might then be able to exploit that to get additional leverage okay。

So I'm actually going to assume here that X just consists not merely of your plain text。

 but your plain text paddted out with a bunch of random ones and zeros at the end that Bob can then ignore。

 okay？Good。Okay， so now how does the encryption work， well。

 the encryption is super duper simple here。😊，It's this， Alice computes X cubed moded。

She sends that to Bob。Okay。Done。Encryption is cubing。Okay， all right。

 now there's only one problem remaining， what's the remaining problem？How yes。

 how does Bob decryptus thing， now he has x cubed and now you know he somehow needs to get from that back to X。

So how does he do that？Right。Okay。So here， you know， of course， you know。

 Bob is going to have to use the fact that he knows the prime factorization， okay。

 and why is that important？Well， if he knows the prime factors P and Q。

 then he also knows p minus1 timesq minus1 okay so Bob knows the order of the multiplicative group okay and in fact on P at6 I believe you proved that that knowing the order of the multiplicative group it' just equivalent to knowing the prime factorization you can get from one from either to the other okay so now。

We use an identity of Euler from the 1760s okay， this is just a small generalization of Fma's little theorem that we saw earlier okay and what this says is that。

是。Okay， so for Bo's little theorem said that if p is a prime。

 then x to the p minus1 is congruent to 1 mod p right that's what it said okay Eer's generalization says that if pq is a composite。

 a product you know namely a product of two primes。

 okay then x to the p minus1 timesq minus1 is congruent to 1 mod pq。Okay， in both cases， you know。

 the proof of it is simply that， well， you know， we're dealing with a group that has that number of elements。

 okay， and you know if you take any element in a group and you multiply it by itself。

 a number of times that equals the order of the group， then you have to cycle back to yourself。Okay。

Yeah， that's。Yeah that's you know a fundamental fact of group theory right you know we have to cycle。

 we have as we multiply， you know we have to be cycling around you know all the elements well either all the elements of the group or all the elements of some subgroup right but if it's a subgroup。

 the order of any subgroup divides the order of the group right so you know we're going to be cycling around an integer number of times and we' going to you know we're going to end up at one all right。

 you know if you didn't believe that argument you know we can do an example。😊。

All so let's say that you know again， p is3，q is5， you know。

 we're going to put Euler's identity to the test， all right。😊。

Someone picking an x for me and acts in the multiplicative group mod 15。14， all right。

So now we've got the problem of 14 to the p minus1 times q minus1 is 8， okay？md 15。All right。

 so we can do this with repeated swearing。You know， it would be easier if you pick the smaller one。

 but what's。All right， do you want to change your answer？All right， good。I like too。All right。

 so what is two to the8 mod 15 well we've got two， two squared is four and now we've got four squared is one right and okay。

 wait wait， I'm sorry。呃。This is two to the two to the two to the two， right， so that's four。

 that's 16。16 mod 15 is one， one squared is still one， okay， so we got one。All right。Good。

You can try it with any of those other elements right。

 you can test it out with four or test it out with 14， if you like。

 check that 14 to the 8 modD 15 equals1。Okay， so， so you cycle around this number of times。

 the order of the multiplicative group， you're going to cycle back to one。basicallysically。

 you know you know we've got these eight things， you know， you know you can get into loops you know。

 but a loop is going to have size two or size4 or size8， okay， so in any case。

 if you go around you know eight times you're going to be back to where you started。

 that's what we're saying here。对。嗯。Okay。So now what this says is that。嗯。mh。

S that Bob could find a K such that 3 k equals 1 mod p minus1 times q minus1。Okay。

 let's just assume for now that he has managed to find such a K then。

We imagine that Bob now takes Alice's cipher text and raises it to the cath power modern in。Okay。

 so the cipher text was x cubed， myan。And now Bob is going to raise that to the k of power， my。

 okay and again， you know， k might be a very large number here。

 so Bob might have to use repeated squaring to do this efficiently， okay， but that's okay。

 you can do that。All right， so then what's he going to get if he does that。

 it's going to get x to the 3K。My dad。Okay but now we already said that 3k is congruent to 1 sorry sorry。

 it's congruent to 1 p minus1 q minus1， so that's like some multiple of p minus1 times q minus1 plus 1。

My okay， and what's this， anyone？Well， this is。呃。X to the p minus1，  Q minus1 to the L。Times X。

 mod N。 And what's that， anyone。This is x， yes， because x to the p minus1q minus1 is just 1 all right。

 so if you can find a K that satisfies this property。

 then by just raising Alice's cipherax to the K then he gets that Bob will get back to x。😊。

Efficiently， all right， so now。You know the only problem is， you know for。

For Bob to find such a k okay but now you know Bob you know has the immense advantage well that at least he knows p minus1 timesq minus1 right he knows what they are。

 okay and now you know once you know that then finding such a K you know is a relatively simple matter you know you've got to sort of figure out you know what is you know the inverse of three。

 you know， mod this okay this is where we use the assumption that p minus1 andq minus1 are not divisible by three。

If they were divisible by three， then this equation might not have a solution but because they are not they're not so divisible that's enough to ensure this product is also not divisible by3 which then tells you that you can divide by3 mod mod the product if it did divide3 then we would have a problem with division because then you could by3 because then you could multiply 3 by something that was non-zero and you could get zero but the fact that the fact that that three does not divide this thing tells you that three is an element of the multiplicative group。

 mod this thing， which means that it's inverse is also an element of the multiplicative group mod this thing。

Okay， which means that this equation has a solution now as for。How to find the solution。

 I think that's on piece at6。Okay， but basically you know you can use Euclid's algorithm。

 you know for the like it's very， very similar to finding the greatest common divisor of two numbers。

 okay， you can very efficiently find a K that satisfies this equation。

 you know if you know p minus1 timesq minus1 so then Bob。

 you know knowing that we'll do this and then he will be able to get x。😊，Okay。All right。

 so then now we just have to consider the situation of Eve， so Eve knows N and she knows。

She knows x cubed mod N right， that was the cipher text okay， and now the Eves problem， if you like。

 as a crypt analyst， is to determine x given n and given x cubed mod N， okay， the problem you know。

That she then faces is to get x， okay that's the RSA decryption problem。

 and now we're going to again just stick our necks out and just assume conjecture that that problem is hard。

 okay。😊，That is called。Wait for it， the RSA is option。Okay， if you give these assumptions names。

 it sounds more respectable。Okay now you know it is clear that you know the RSA assumption can be no more secure than you know the assumption that factoring is hard right。

 if you have a fast factoring algorithm， then certainly you can break RSA okay once again the converse of that is actually not known it's you know an open problem to present to the present。

 okay just like no one knows how to prove that breaking diiffy Heman is you know is equivalent to discrete logarithm。

 okay you know it's a dirty little secret right no one knows how to prove that breaking RSA is equivalent to factoring。

😊，it is conceivable that it could be easier。Oh anyone can send messages to Bob， sure， you know。

 Eve can say， you know， hey， you know， I'm your enemy， I hate you， you know， and you know。

 I've encrypted this message， you know， and Bob will be like whatever， you know。

 I was just trying to talk to Alice， you know， so I mean。Yeah， yeah。

 so the system does have the property that everyone knows Bob's public key and because of that。

 everyone can send encrypted messages to Bob okay， but we're happy you know as long as you know for each person who sends encrypted messages to Bob。

 Bob is the only one who can read those messages because only Bob knows the private key。Yeah，hu。Good。

Yeah， good point okay you know now you know you know there are all sorts of you know issues that you worry about in practice like for example you know the whole system is vulnerable to what's called a man in the middle attack okay which would say you know if Eve could just take control of the communication channel and pretend to be Bob okay you know and if she could just you go on the internet and like convince Alice that she is Bob and then send you know send a public key that Alice thinks is Bob's key but it's actually Eve's key right and then send the message will then Eve can you know surprise surprise。

 Eve can then read it okay so this is why you know this entire scheme relies on you know public keys you know being you know communicate it like in you know in an uncorruptible way okay so this is why you have these like on。

The internet， you have these public key registries like these like trusted companies that you know know Verign or whatever that say。

 here we have this registry of public keys we're going to certify as really being from the people that they're claimed to be from。

Okay。So that's you that is something that you need right。

 so you know if you like the attack model that we're assuming here is that yes。

 can eavesdrop on the channel， but you can't control the channel and pretend to be Bob， okay。

 because if she could do that then we're just helpless。呃。Okay， other comments to make。

 so you know the way that RSA is commonly presented， you know。

 you know Eve could be raising to some other sorry Alice could be raising to some other power other than three right she could raise to the fifth power you know the tenthth power that you know can you know you know in fact you know the exponent you was often just called E right and that's you know just some number that Alice raises to and that everyone knows。

 okay I simply chose three for this presentation of RSA because three is the smallest number that works。

why is that， anyone？呃。Why would two not or what would have been the problem with using two？Well。

 it's okay， so one okay， here's this is actually an interesting question because actually you know there is a crypto system that。

That involve squaring mode。 All right， so you can try it， but I'll tell you what happens。 All right。

 This is called the ran crypto system。Okay， and。The innovation of the ran system is that instead of cubing modan。

 you square modan。Okay， and， Alice would then send this to Bob。😊，Now the ran system actually has。

 you know， it does have a huge advantage compared to RSA and that this is the Raven system。

 Ran was actually able to prove that breaking this system is equivalent to factoring in okay if you could break the raven system。

 then you can factor in okay。Yeah I guess I guess I won't show the proof here but it's not too hard。

 just a little bit of number theory but the Raven system also has a disadvantage that a reason why people don't usually use it in practice okay and the disadvantage is that the decryption is not unique there could be multiple you plain texts that correspond to a given cipher text and this has to do with the fact that taking square roots is not unique okay you all know that the same number could have multiple square roots and the same is true and we work modo you numbers like this so in fact if you want unique square know basically the rule is that if you wanted unique K。

Ros， then P -1 and Q -1 have to be not divisible by k。

That what's going to put that's what's going to make this equation solvable so we need or I should use a different number。

Someone give me a different variable name。T， yes， good choice if we want teaeth roots to exist and always exist and always be unique。

Let me write that。Teeeth roots。Mod N， you know， or modd PQ exist and are unique。So in other words。

 decryption is unique if and only if。P minus1 and Q minus1 are not divisible by t。😡，Okay。

 with or actually， you know， I should say p minus1 and Q minus1 share no common factor with T。Okay。

 if you know， in general， a 50 is composite， right？Okay， so。U。if you don't have this。

 then first of all， the roots could be non unique when they do exist and secondly。

 roots just simply might not exist。What's a good example。诶。Yeah， what's the square root of two mod3。

 for example， right， what is it that when you square it mod3 that you get two？Nothing。You know。

 one squared mod3 is one， two squared mod3 is also one okay。

 so you get a collision and you know one has two square roots and two has no square roots okay so that's a problem that means you know that there is some ciphertex that has no plain text corresponding to it and there is some you know ciphertex that has two different plane text corresponding to it and you would then have to throw one of them out as you know。

 maybe you would look at it and see that it was gobbledy g okay but。All right。

 but now we can say what's the issue， what is now the issue here if T is2？

Let's see what problem arises here what special problem arises if t is2？Yeah。Excellent。And yes。

 and even prime numbers are not very common， okay， in fact， there's exactly one of them。

 okay so you know every other prime number， p you know other than two。

 you take p minus1 and it is divisible by  two。Okay， there's your problem right。

So so you're not going to be able to avoid this problem of having multiple valid decryptions， okay。

 and this is why we used cubing instead of squaring if we wanted unique decryption。😊，嗯。Okay。

Okay so if we want to abstract what's going on with the RSA crypto system， you know。

 there's a concept that abstracts it， which is called a trapor one way function or to d。Okay。

 so on Thursday we defined one way functions right。

 it's a family of functions that is easy to compute but intractable to invert okay a trapor one way function is a family of one way functions that has an additional property okay。

😊，So I'm not going to give the formal definition， I don't think it's。Not important， but it's。

So it's a family of functions like this， you know， I'll say like parameterized。

 you know by some s so I'll give you some s that helps you compute this function。

 so there may be many， many of these for each input length n like an exponential number of different ones。

 okay and given it S you can compute the function， given only s you know the function is intractable to invert to find pre-images。

 however， and this is now the thing that makes a trappedor。

 there is some secret that you could know other than s。

 that if you know it would make this function easy to invert。Okay， so there is。

 so it's easy to compute。It's hard to invert。But there is some secret。There is a secret key。

That makes it again easy to invert in the specific example of RSA， the function。

I'll say let me let me say it depends on n right the function is just is cubing mod n okay that is our trapor one way function this is you know if you only know n。

 then we believe that this function is hard to invert however。

 if you know a secret namely the prime factors of n then this function becomes a cubing mod n becomes easy to invert okay and so that that's what a trapor one way function means and。

And it's known in some precise sense that。Trap door oneway functions are sort of the necessary and sufficient thing that you need in order to have public key cryptography。

So you know this is like in the same way that ordinary oneway functions are the resource that you need for private key cryptography Traor oneway functions are the thing that you need for public key cryptography okay and trapor oneway functions are inherently much more special than regular one-way functions okay you know what I told you at the beginning of the lectures you know a regular ordinary oneway function you know you could just make up some kind of random you know scrambling transformation of your input so you know run some cellular automaton or run Conway's game of life or you know multiply your number you know take the middle digits you know chop them up。

 you know rearrange them in some stupid way you know it's a good chance it'll be one way okay you know no one will know how to invert what you just did okay。

Okay but now if you want a trap door whatway function。

 now you know there has to be some secret that you can tell someone that makes your functions suddenly easy to invert again okay that is a much more special property and that you know we only know how to achieve for you know problems that have some very nice mathematical structure to them like you modular exponentiation。

 like Qing mod N where we have all this number theory at our disposal okay and this is sort of the tradeoff that is you know in like the curse of cryptography right the more you want to do like if you want public key crypto you know you want other interesting stuff the more you want to do the more mathematical structure you need in order to do it but then the more mathematical structure you have you know like the further you are from like the completely generic case of being you like an NP complete problem。

or you something that just requires brute force， right。

 the more clever attacks there might be open to an adversary， if not classical attacks。

 maybe quantum attacks。Okay。So。So there's a very nice way to sort of organize our knowledge。

 you know our understanding of what are the possible worlds like that we could be living in with respect to cryptography。

 okay and due of Russell and Palyazto these are not terms that you'll need to know for the final or anything like that okay but this is just a helpful way to to organize your understanding of this so what he says basically is that there are five possible worlds that we could be living in。

The first world because algorithmica。And this is the world where p equals NPp。

OkayYou know and in this world I' right algorithms are just super duper powerful right they can you know well they can solve NP right you know you can do any NPp complete problem in polynomial time okay but you know the dark side of that if you like is that you know we can have no cryptography other than the onetime pad or other than you know quantum cryptography you know on the whole that's probably you a good tradeoff okay but you know but but you know in this world there' there's no like secure computational cryptography that that's ever going to work okay you know but buttp equals NP okay。

😊，Okay， the second world is called horistica， okay and this is。This is a world where。

Where P is not equal to NP， but all NP complete problems are easy to solve in the average case okay。

 so you know， if I give you any like efficient algorithm that samples a a probability distribution over。

NP complete problem instances that there will be a polynomial time algorithm that solves most of the instances drawn from that distribution that's what we mean okay so you know so that is also a possible world and it's even possible if you believe that P is not equal to NP so this would be a strange situation that you know like P would not equal NP but you know finding the hard instances of NP complete problems but itself be a hard problem right you know know we would hardly ever run into the instances that were actually hard okay so you could say that like for practical purposes it would be almost as if P equal to NP okay and in particular cryptography is also not going to be possible in this world right because if you can't reliably generate hard problems then you you don't have crypto。

Okay， you know， but of course， you have super powerful algorithms。😊，Okay。

 the third world he calls pessy land， okay this is you know the most pessimistic case。

 the worst of everything okay， this is the world where NP complete problems can be hard on average。

 but we cannot leverage that to construct one-way functions okay so yes。

 there are NP complete problems， yes they're hard on average。

 but we still don't have cryptography okay not even private key cryptography okay and basically you know yes。

 we can generate you know hard problems， but we can't generate them at the same time that we the generator also know the solution to them。

😊，Okay， and you know， because of that， you know， and that's sort of the thing that you need for one way functions as you're going to prove on P at six。

Okay，U。The fourth world is called MinCrypt， this is where one way functions exist but not trapor one way functions。

 Okay， so here we've got you know private key cryptography but not public key cryptography。

And then the fifth world， he calls cryptomania。And。That's where trap door wideadway functions exist。

 Okay， so you know， as far as we can tell today， we seem to live in cryptomania。Okay， but you know。

All what。All right， so now you in the last。Five or eight minutes or whatever。

 I want to tell you a really， really cool application of RSA okay。

OkayThis is what we call the dating protocol okay so the basic problem we face is this right Alice and Bob you know would like to know you know if they're both interested in dating each other okay but you know they are shy computer scientists okay so so the problem is that if you know if they're both interested in each other they would both like to know that but if let's say Alice is interested and Bob is not then Alice would like would not like Bob to ever find out that she was interested okay and vice versa okay of course you know whoever is interested you know will find out you know with whether the other one was interested you know that's unavoidable。

 you might say okay but whichever you know anyone who is not interested should not find out whether the other。

One was interested okay that' that's the problem this is a well known problem well one might say you know traditionally it's been solved in a variety of ways for example the trusted third party method okay where they both you know confide in some mutual friend okay the problem with that of course is that you really do have to trust the third party right you know not not to gossip or not to you know and that's not always a safe assumption okay you know there are other don' you know if anyone want to suggest other ways to solve this you know the。

I had a student one year who suggested， you know， the way to solve this is you。

 have Alice and Bob just face each other with their eyes closed and then you whichever one is interested should open their eyes。

Okay， you know， that seems to work until you consider， well。

 what if neither is interested and they just stand there with their eyes closed forever？😊。

So remember， they're computer scientists， okay all right。😊。

You know you could imagine you can try to think about you how else to do this。

 but here you know I will show you how to do it using RSA。

 okay use it using cryptography okay now you know a few you know caveats before we start okay。

 one is if。嗯。Let's see， so we're never going to be able to solve the problem that you know。

 like Alice could pretend to be interested， you know， if she could say that she is and then you know。

 and then find out Bob is interested then she says， well，ha ha， I'm not actually。

 I just wanted to find out whether you were。We can't deal with that， sorry。

Okay all we can do is to make sure that if one party。

 you know you know that in order to find out whether one the other party has expressed interest。

 you have to express interest okay。😊，What else？嗯嗯。嗯。Oh yeah， okay。

 you might say that you know the very fact that they're carrying out this protocol at all is sort of prima fussy evidence that maybe they you know if if someone suggests to you to do this protocol right。

 then maybe you know that arouses your suspicions okay but you know so we should imagine that they're at some party like you know a cryptographer's party where like every pair of people is supposed to do this okay。

All right， so now。How are we going to do it？All right well。You know the usual way these things start。

 Alice picks two huge random prime numbers， P and Q， all right？Very important。

P minus1 and  Q minus1 are not divisible by 3。She finds their product and。s PQ， know。

 she keeps P and Q secret， but you knows she sends an over to Bob okay and she is also going to create she's also going to send Bob。

Two numbers x cubed mod n and y cubed mod n Okay what are these Well if Alice is not interested in Bob。

 then X and y are just both going to be zeros paddted out with a bunch of random garbage okay you know so elements of the multiplicative group that just encode a zero okay。

That's how she says she's not interested。 If Alice is interested。

 then x is0 padded out with lots of random garbage。

 whereas Y is one padded out with lots of random garbage。出。Okay， so so you know， already， you know。

 if Bob could compute Q roots mod end， he could find out if Alice was interested， right。

 but you know again， we're going to assume RSA is secure so he can't compute cube roots mod end。

 all right。Next step。呃。Bob picks， you know what。嗯。😊，Yeah， okay。

 Bob picks a random element R in the multiplicative group mod end if。If Bob is not interested。

 then he is going to send back to Alice X cubed R cubed modern， if Bob is interested。

Then he is going to send back why cubed are cubed by that。All right。So you know now Alice， you know。

 because she knows P and Q， she knows how to calculate Q roots module N， right that's you know。

 she knows how to do RSA decryption， so she can now take a Q root of this thing to get either you know XR mod N if Bob wasn't interested or YR mod N if Bob was interested。

Right， see that okay but now you know this still gives Alice no real information because R was completely random。

 okay so R has just completely randomized the information you know of Bob's interest okay so you know just like with the one time pad okay。

So what can she do with this well you know， all she can do is she can take this random looking number that she has and she can send it back to Bob okay。

 so she sends it back to Bob。I said， what can Bob do anyone？He has either XR or YR。Well。

 he can divide by R right he can divide by R， which means that if he didn't say that he was interested。

 then you know he now has just simply X if he said he was interested。

 then he now has Y so in other words， only if he said he was interested。

 does he have Y which is the thing that would tell him whether Alex wire doesn't give him away so there you go that's the protocol now we did make a crucial assumption you know in this protocol which is we assumed that the parties were actually doing what they were post terms but they were in cheating and sending a message or not to post。

Okay， when Robin lectures on Tuesday， he'll tell you about how you can remove that assumption using an amazing idea called zero knowledgeledge proofs。

 okay and then if there's time then he may get started on quantum computing okay and then on Thursday we'll be doing our quantum computing unit all right。

And yeah， I've got PS at four here to pick up if you'd like。

